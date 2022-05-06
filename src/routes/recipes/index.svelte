<script lang="ts">
    import { markdown } from "markdown";
    import { onMount } from "svelte";    
    var url = "";
    var qdata = "";
    onMount(() => {
        url = "http://127.0.0.1:8000/recipes/".concat(window.location.href.substr(32));
        fetch(url)
            .then(res => res.json())
            .then(dat => qdata = dat.recipe);
    });//get query
</script>
{qdata}