<script>
    // 列表渲染
    let arr = [
        {id:1,name:"aa",age:18},
        {id:2,name:"bb",age:19},
        {id:3,name:"cc",age:20},
        {id:4,name:"dd",age:21},
        {id:5,name:"ee",age:22}
    ]
</script>

<ul>
    {#each arr as item, index (item.id)}
        <li>
            index:{index}
            id: {item.id}
            姓名: {item.name}
            年龄: {item.age}
        </li>
    {/each}
</ul>