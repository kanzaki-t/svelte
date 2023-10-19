<script>
    import { onMount, onDestroy, beforeUpdate, afterUpdate } from "svelte";

    // dom节点更新前
    beforeUpdate(async () => {
        // 用于记录dom节点更新前的状态
        alert("beforeUpdate");
    });

    // 挂载期
    onMount(async () => {
        // 一般可以通过挂载来进行网络请求
        alert("onMount");
    });

    // dom节点更新后
    afterUpdate(async () => {
        // 在dom接口更新后所需事件
        alert("afterUpdate");
    });

    // 卸载期
    onDestroy(async () => {
        // 卸载工作，例如释放变量，删除时钟
        alert("onDestroy");
    });
</script>

<h1>生命周期</h1>