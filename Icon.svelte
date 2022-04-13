<svelte:options/>

<script lang="ts">
    export let expression: string;
    let string
    $: if(expression) {
        const parsed = JSON.parse(expression)
        if (parsed.data) {
            string = JSON.parse(parsed.data)
        } else {
            string = parsed
        }
    }
</script>

<div class="container">
    {#if expression}
        <input disabled bind:value={string}>
    {/if}
</div>


<style>
    .container {
        color: burlywood;
        width: 400px;
        height: 300px;
    }

    input {
        width: 100%;
        height: 300px;
        color: black;
        background: yellowgreen;
        text-align: center;
        font-size: 20px;
    }
</style>