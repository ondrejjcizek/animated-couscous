<script lang="ts">
    let buttonIsActive = false;

    const buttonHandler = () => {
        if (buttonIsActive) {
            buttonIsActive = false;
        } else {
            buttonIsActive = true;
        }
    };
</script>

<button
    on:click={buttonHandler}
    class:active={buttonIsActive}
    class="block h-10 w-20 rounded-full bg-gray-500 p-1"
>
    <span
        class="circle left-0 top-0 flex h-full w-8 translate-x-0 rounded-full bg-white duration-1000"
    />
</button>

<style lang="postcss">
    .circle {
    }

    .active {
        span {
            animation: animateCircle 1s;
            transition: transform 2s;
            @apply w-8 translate-x-[calc(100%+8px)];
        }
    }

    @keyframes animateCircle {
        0% {
            @apply w-8 translate-x-0;
        }

        33.3% {
            @apply w-6 translate-x-[33.3%];
        }

        66.6% {
            @apply w-6 translate-x-[calc(100%+8px)];
        }

        100% {
            @apply w-8 translate-x-[calc(100%+8px)];
        }
    }
</style>
