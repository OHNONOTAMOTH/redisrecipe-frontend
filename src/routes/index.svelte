<script lang="ts">
    let query = "";

    function submitsearch() {
        window.location.replace("search?q=" + query)
    }
</script>
<div class="flex justify-center self-center items-center hover:shadow">
    <input class="rounded hover:shadow bg-gray-500" bind:value={query}>
    <button class="hover:shadow rounded" on:click={submitsearch}>search</button>
</div>