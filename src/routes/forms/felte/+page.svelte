<script lang="ts">
    type Error = {
        email: string;
        password: string[];
    };

    import { createForm } from 'felte';

    let emailValidate: string;
    let passwordValidate: string;

    const { form } = createForm({
        onSubmit(values, context) {
            console.log(values);
            context.reset();
        },
        onSuccess(response, context) {
            console.log(`onSuccess: ${response}, ${context}`);
        },
        onError(err, context) {
            console.log(`onError: ${err}, ${context}`);
        },
        validate: (values) => {
            const errors: Error = {} as Error;
            if (!values.email || !/^[^@ \t\r\n]+@[^@ \t\r\n]+\.[^@ \t\r\n]+/.test(values.email)) {
                errors.email = 'Must be a valid email';
            }
            if (!values.password)
                errors.password = ['Must not be empty', 'Must be over 8 characters'];
            if (values.password && values.password.length < 8) {
                errors.password = ['Must be over 8 characters'];
            }
            console.log(errors.email);
            console.log(errors.password);
            return errors;
        }
    });
</script>

<form use:form>
    <input type="text" name="email" />
    <input type="password" name="password" />
    <button type="submit">Sign In</button>
</form>
