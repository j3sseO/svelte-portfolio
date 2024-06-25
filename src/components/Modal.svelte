<script>
    export let show = false;
    export let step;
    export let onClose;
</script>

<!-- svelte-ignore a11y-no-static-element-interactions -->
{#if show}
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div
        class="fixed inset-0 bg-black border-solid
    border-violet-700 bg-opacity-50 flex justify-center items-center z-50"
        on:click={onClose}
    >
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div
            class="bg-black p-6 rounded shadow-lg max-w-lg w-full relative"
            on:click|stopPropagation
        >
            <button
                class="absolute top-2 left-2 text-gray-500 hover:text-gray-700"
                on:click={onClose}
            >
                <i class="fa fa-times"></i>
            </button>
            <h3 class="text-2xl mb-4">{step.name}</h3>
            <p>{step.description}</p>
        </div>
    </div>
{/if}
