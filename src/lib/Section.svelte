<script lang="ts">
    export let title:string;
    export let description:string;
</script>   

<div id="{title}">
    <h2>{title}</h2>
    <p>{description}</p>
    <slot/>
</div>

<style>
    p {
        max-width: 800px;
    }
    div {
        margin-left: 1rem;
        margin-right: 1rem;
        min-height: 60vh;
        margin-top: 5rem;
    }
    h2 {
        font-size: 1.8rem;
    }
</style>