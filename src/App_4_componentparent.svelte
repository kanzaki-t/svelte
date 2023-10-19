<script>
    import Componentchild from "./App_4_componentchild.svelte";

    // 父传子的另一个方法，子传父则出错
    import { setContext } from "svelte"
    setContext("mykey",{
        msg:"来自父组件的信息"
    })
</script>

<div>
    <p>我是父组件</p>
    <br />

    <Componentchild />
    <br />

</div>