<script>
    // 条件渲染
    let flag = false
    let flag1 = true
</script>

{#if flag}
    <div>true</div>
{:else if !flag && flag1}
    <div>aaaaa</div>
{:else}
    <div>false</div>
{/if}

<button on:click={() => flag = !flag}>点我</button>