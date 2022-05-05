<!-- <script lang="ts">
    import { onMount } from "svelte";
    import { browser } from "$app/env";

    let url = "";

    onMount(() => url = window.location.href.substr(31)); //get query
    let xhr = new XMLHttpRequest();
    let resp = "";

    xhr.open("GET", url);

    xhr.onload = () => {
        resp = xhr.response;
        console.log(resp);
    }
    
    xhr.send();
</script>
{resp}
{url} -->
<!--<script lang="ts">
    import { browser } from '$app/env';
    import { onMount } from "svelte";
    let url = "";
    let resp = "";
    if (browser) {
        onMount(() => url = ("www.google.com/" + window.location.href.substr(31))); //get query
        console.log(url);
        let xhr = new XMLHttpRequest();
        xhr.open("GET", url);
        xhr.onload = () => {
            resp = xhr.response;
            console.log(resp);
        }
        xhr.send();
    }
</script>-->
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

<div class="grid justify-center rounded bg-slate-500">
    {#each qdata as result}
        <p>{result}</p>
    {/each}
</div>