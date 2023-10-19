<script>
    /**
     * 事件
     * 
     * 修饰符：
     * preventDefault: 停止默认事件
     * stopPropagation: 停止冒泡
     * passive: 提高滚动性能
     * nonpassive: 显示的设置
     * capture: 捕获阶段处理事件
     * once: 只执行一次，完了后移除事件，使得下次不能被执行
     * self: 仅在事件对象event.target为元素本身时执行事件
     * trusted: 只有event.isTrusted 是 true 才进行触发
    */
   const onceclick = () => {
    console.log("aaa")
   }

   let count = 0
   const addclick = () => {
    count++
   }
   const deleteclick = () => {
    count--
   }

   let price = 100

   // $ 符号是 Svelte 中非常强大的工具，反应式声明,用于构建高度响应性的用户界面，
   // 减少了手动更新 DOM 的繁琐工作。通过响应式绑定，你可以更容易地实现复杂的数据驱动视图更新。
   $: message = `Count is ${count}`
</script>

<!-- 带修饰符的写法 -->
<button on:click|once={onceclick}>点我</button>
<br />
<br />

<!-- 响应式数据 -->
<button on:click={deleteclick}>-</button>
{count}
<button on:click={addclick}>+</button>
<br />
价格：{price}
{message}