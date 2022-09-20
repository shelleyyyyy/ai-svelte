<script>
    import RowItem from "./RowItem.svelte";
    export let arr;
</script>

<div class="flex gap-2">
    {#each arr as item}
        <RowItem item={item}></RowItem>
    {/each}
</div>

<style>
    .test{
        height: 20%;
    }
</style>