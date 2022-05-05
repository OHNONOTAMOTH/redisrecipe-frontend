<script lang="ts">
    import { onMount } from "svelte";    
    var url = "";
    var qdata = Object.create(null);
    onMount(() => {
        url = "http://127.0.0.1:8000/apisearch/".concat(window.location.href.substr(31));
        fetch(url)
            .then(res => res.json())
            .then(dat => qdata = dat.results);
    }); //get query
    var h = "http://127.0.0.1:8000/apisearch/".concat(url);
</script>

<div class="grid rounded justify-center hover:shadow">
    {#each qdata as result}
        <div class="rounded hover:shadow m-100">
            <p>{result}</p>
        </div>
    {/each}
</div>