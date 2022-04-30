<script lang="ts">
    let query = "";

    function submitsearch() {
        window.location.replace("search/" + query)
    }
</script>
<div class="flex justify-center self-center items-center hover:shadow">
    <input class="rounded" bind:value={query}>
    <button class="hover:shadow" on:click={submitsearch}>Submit</button>
</div>