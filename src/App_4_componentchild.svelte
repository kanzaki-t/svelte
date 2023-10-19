<script>
import { getContext } from "svelte"
const context = getContext("mykey")

</script>



<div>
    我是子组件

    <!-- 父传子的另一个方法 -->
    {context.msg}
</div>