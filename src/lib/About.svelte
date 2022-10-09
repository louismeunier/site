<script>
    import { fly } from "svelte/transition";
</script>


<div transition:fly={{x:500,duration:300}}>
    <h2>hey!</h2>
    <p>this is my personal website, made to display some of my personal projects and interests.</p>
    <p>enjoy :)</p>
</div>

<style>
    div {
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        justify-content: center;
    }
    div > * {
        margin-right: 1rem;
    }

    h2 {
        font-size: 1.8rem;
    }
</style>