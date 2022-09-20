<script>
    import {
        Walk,
        ChevronUpOutline,
        ChevronDownOutline,
        ChevronForwardOutline,
        ChevronBackOutline,

    } from "svelte-ionicons";

    // get grid diminseions
    let diminsions = 7

    export let item;
    let calc = 48/diminsions;
    let size = String(calc) + "rem"
</script>

{#if "o" == item}
    <div style:height={size} style:width={size} class="p-5 shadow-xl w-full">
        <!-- {item} -->
    </div>
{/if}

{#if "c" == item}
        <div style:height={size} style:width={size} class=" bg-black text-white p-5 shadow-xl w-full">
            <!-- {item} -->
        </div>
{/if}

{#if "a" == item}
    <div style:height={size} style:width={size} class=" flex justify-center bg-red-700 text-white p-5 shadow-xl w-full">
        <Walk size="fit" />
    </div>
{/if}  

{#if "p-u" == item}
    <div style:height={size} style:width={size} class="flex justify-center bg-gray-400 text-white p-5 shadow-xl w-full">
        <ChevronUpOutline size="fit" />
    </div>
{/if}  

{#if "p-r" == item}
    <div style:height={size} style:width={size} class="flex justify-center bg-gray-400 text-white p-5 shadow-xl w-full">
        <ChevronForwardOutline size="fit" />
    </div>
{/if}  

{#if "p-d" == item}
    <div style:height={size} style:width={size} class="flex justify-center bg-gray-400 text-white p-5 shadow-xl w-full">
        <ChevronDownOutline size="fit" />
    </div>
{/if}  

{#if "p-l" == item}
    <div style:height={size} style:width={size} class="flex justify-center bg-gray-400 text-white p-5 shadow-xl w-full">
        <ChevronBackOutline size="fit" />
    </div>
{/if}  