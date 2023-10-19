<script>
    // 父传子
    export let msg = ""

    // 子传父
    import { createEventDispatcher } from "svelte"
    const dispatcher = createEventDispatcher()
    const sendtoparent = () => {
        dispatcher("aaa","子组件传过来的信息")
    }
</script>



<div>
    我是子组件

    <!-- 匿名插槽，可以从父组件上拿到信息 -->
    <slot />

    <!-- 具名插槽，可以从父组件上拿到信息 -->
    <slot name = "block1"></slot>
    <slot name = "block2"></slot>

    <!-- 父传子 -->
    {msg}

    <!-- 子传父 -->
    <button on:click={sendtoparent}>子传父</button>
</div>