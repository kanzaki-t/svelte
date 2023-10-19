<script>
    import Componentchild from "./App_3_componentchild.svelte";
    let msg1 = ""
</script>

<div>
    <p>我是父组件</p>
    <br />

    <Componentchild />
    <br />

    <!-- 匿名插槽 -->
    <Componentchild>匿名插槽信息</Componentchild>
    <br />

    <!-- 具名插槽 -->
    <Componentchild>
        <div slot="block1">具名插槽block1</div>
        <div slot="block2">具名插槽block2</div>
    </Componentchild>
    <br />

    <!-- 父传子 -->
    <Componentchild 
        msg= "父组件传过来的数据"
    />
    <br />

    <!-- 子传父 -->
    <Componentchild 
    on:aaa={ e => {
        console.log(e)
        msg1=e.detail
    }}
    />
    {msg1}
</div>