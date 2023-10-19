<script>
    /**
     * 直接修改数组或对象，svelte无法识别被修改的数组和对象，
     * 进而无法即使渲染画面
     * 
     * 通常通过浅拷贝和深拷贝的形式来解决
     * 
     * 对象：
     *  Object.assign({},obj1,obj2) 从后往前合并，同样的key的情况下，后面的会覆盖前面的同key的内容
     *  {...obj1,...obj2} 浅复制
     *  JSON.parse(JSON.stringify(obj1)) 深拷贝
     * 
     * 数组：
     *  [...arr1,...arr2] 浅复制
     *  JSON.parse(JSON.stringify(arr1)) 深拷贝
     *  
    */

   let arr = [1,2,3]

   $: total = arr.reduce((total,curr) => total = total + curr,0)

   const change = () => {
    arr.push(arr.length +1)
    // arr = [...arr]
    arr = JSON.parse(JSON.stringify(arr))
   }
</script>

<div>
    {arr.join(" + ")} = {total}
</div>

<br />

<button on:click={change}>aaa</button>