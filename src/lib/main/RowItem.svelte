<script>
    export let item;
    let calc = 48/7;
    let size = String(calc) + "rem"
</script>

<div style:height={size} style:width={size} class="p-5 bg-black text-white w-full">
    {item}
</div>
