<script>
  let name = "神崎";
  const src = "../public/vite.svg";
  let check = false;
  let check1 = false;

  function checkboxOnClick() {
    check = !check;
  }

  let books = [];
  let books1 = [];

  let select = "0";
  function handleSelectChange(e) {
    select = e.target.value;
  }
</script>

<main>
  <div>hello {name}</div>

  <!-- 这里的src是简写之后的结果，正常是src = {src} -->
  <br />
  <img {src} alt="false" />

  <!-- 使用 bind 来实现双向绑定 -->
  <br />
  <input type="text" bind:value={name} />

  <!-- 使用 on:click 来实现事件触发 -->
  <br />
  <input type="checkbox" checked={check} on:click={checkboxOnClick} />
  {check}
  <br />
  <input type="checkbox" bind:checked={check1} />
  {check1}

  <!-- 复选 -->
  <br />
  <input type="checkbox" bind:group={books} name="books" value="选项1" />
  <input type="checkbox" bind:group={books} name="books" value="选项2" />
  <input type="checkbox" bind:group={books} name="books" value="选项3" />

  <!-- 单选 -->
  <br />
  <input type="radio" bind:group={books1} name="books1" value="选项1" />
  <input type="radio" bind:group={books1} name="books1" value="选项2" />
  <input type="radio" bind:group={books1} name="books1" value="选项3" />

  <!-- 下拉菜单 -->
  <br />
  <select bind:value={select} on:click={handleSelectChange}>
    <option value="0" />
    <option value="1">选项1</option>
    <option value="2">选项2</option>
    <option value="3">选项3</option>
  </select>
  <br />
</main>

<style>
</style>
