<script>
    async function sleep(time) {
        return new Promise((resolve,reject) =>{
            
            setTimeout(() => {
                resolve("time over")
            }, time);
        })
    }
</script>

{#await sleep(3000)}
    Loading...
{:then res} 
    {res}
{/await}