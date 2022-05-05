<script lang="ts">
    let query = "";

    function submitsearch() {
        window.location.replace("search?q=" + query)
    }
    let x = "<h1>kjgjghjhg</h1>";
</script>
<div class="flex justify-center self-center items-center hover:shadow">
    <input class="rounded" bind:value={query}>
    <button class="hover:shadow" on:click={submitsearch}>Submit</button>
</div>