<script>
    // 补间动画（类似于进度条）
    import { tweened } from "svelte/motion";
    import { cubicOut } from "svelte/easing";

    const progress = tweened(0, {
        duration: 2000,
        easing: cubicOut,
    });

    // spring动画（具有弹性）
    import { spring } from "svelte/motion";

    const progress1 = spring(0, {
        stiffness: 0.1,
        damping: 0.25,
    });

    // 显隐式动画
    import { fade, fly } from "svelte/transition";

    let show = false
</script>

<!-- 补间动画（类似于进度条）-->
<progress value={$progress} />
<button on:click={() => progress.set(0)}>0%</button>
<button on:click={() => progress.set(0.5)}>50%</button>
<button on:click={() => progress.set(1)}>100%</button>

<br />

<!-- spring动画（具有弹性）-->
<progress value={$progress1} />
<button on:click={() => progress1.set(0)}>0%</button>
<button on:click={() => progress1.set(0.5)}>50%</button>
<button on:click={() => progress1.set(1)}>100%</button>

<br />

<!-- 显隐式动画-->
{#if show}
    <p transition:fade>aaaa</p>
    <p transition:fly={{y:200, duration:2000}}>ffffff</p>
    <p in:fly={{y:400, duration:2000}} out:fade>eeeeeeeee</p>
{/if}
<button on:click={() => {show = !show}}>显隐式动画</button>
