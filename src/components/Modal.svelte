<script>
    import { fade } from "svelte/transition";
    import { browser } from '$app/environment';
    export let show = false;
    export let step;
    export let onClose;

    function disableScroll() {
        if (browser) {
            document.body.classList.add('no-scroll');
        }
    }

    function enableScroll() {
        if (browser) {
            document.body.classList.remove('no-scroll');
        }
    };

    $: if (show) {
        disableScroll();
    } else {
        enableScroll();
    }
</script>

<!-- svelte-ignore a11y-no-static-element-interactions -->
{#if show}
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div
        class="fixed inset-0 bg-black bg-opacity-50 flex justify-center items-center z-50"
        on:click={onClose}
    >
        <div
            class="fixed inset-0 bg-black bg-opacity-50"
            transition:fade={{ duration: 400 }}
            aria-hidden="true"
        ></div>
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div
            class="bg-slate-950 p-8 10xl:flex 10xl:flex-row rounded-lg border-4 border-solid
                border-violet-700 shadow-lg overflow-y-auto max-h-full sm:max-w-5xl w-full relative p-200"
            transition:fade={{ duration: 400 }}
            on:click|stopPropagation
        >
        <div>
            <h3 class="font-medium text-3xl mb-4">{step.name}</h3>
            <p class="pr-4">{@html step.description}</p>
            <br />
            <a href={step.repolink} target="_blank">
                <button
                    type="button"
                    class="text-white bg-gray-800 hover:bg-gray-900 focus:outline-none focus:ring-4 focus:ring-gray-300 font-medium rounded-full text-sm px-5 py-2.5 me-2 mb-2 dark:bg-gray-800 dark:hover:bg-gray-700 dark:focus:ring-gray-700 dark:border-gray-700"
                    >Project Repository</button
                >
            </a>
        </div>
        <button
            class="absolute top-1 left-2 text-gray-500 hover:text-gray-700"
            on:click={onClose}
        >
            <i class="fa fa-times"></i>
        </button>
            <div class="10xl:pr-5 block">
                <img
                    src={step.image1}
                    alt="image1"
                    class="10xl:max-w-[40vh] rounded pb-4"
                />
                <img
                    src={step.image2}
                    alt="image2"
                    class="10xl:max-w-[40vh] rounded"
                />
            </div>
        </div>
    </div>
{/if}
