<svelte:options/>

<script lang="ts">
    let text = ""
    function commitExpression(e) {
        e.target.dispatchEvent(new CustomEvent('commitExpression', { detail: { text }, composed:true }))
    }

    function discard(e) {
        text = ""
        e.target.dispatchEvent(new CustomEvent('discard', { composed:true }))
    }
</script>

<div class="container">
    <input bind:value={text}>
    <button on:click={commitExpression}>Commit</button>
    <button on:click={discard}>Discard</button>
</div>


<style>
    .container {
        color: burlywood;
        width: 400px;
        height: 300px;
    }

    input {
        width: 100%;
        height: 200px;
    }
</style>