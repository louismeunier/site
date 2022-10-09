<script>
    import { fly } from "svelte/transition";

    const projects = [
        {
            title: "cycling tracker",
            description: "",
            source: "https://github.com/louismeunier/bike",
            link: "https://bike.louismeunier.net",
            image: "bike.png"
        },
        {
            title: "college email analysis",
            description: "",
            source: "https://github.com/louismeunier/college-emails",
            link: "https://college-emails.louismeunier.net",
            image: "collegeemails.png"
        },
        {
            title: "botting@home",
            description: "",
            source: "https://github.com/Cubing-at-Home/cubingathome-bot",
            image: "bottingathome.png"
        }
    ]
</script>
<div class="programming" transition:fly={{x:500,duration:300}}>
    {#each projects as project, i}
        <div class="project">
            {#if i%2 == 0}
                <div class="description left">
                    <h4>{project.title}</h4>
                    <!-- <p>auto-updating map of my bike rides</p> -->
                    <div class="links">
                        <a href={project.source}>source </a>{#if project.link} // <a href={project.link}>site</a>{/if}
                    </div>
                </div>
                <img width="300em" src={`${project.image}`} alt="placeholder">
            {:else}
                <img width="300em" src={`${project.image}`} alt="placeholder">
                <div class="description right">
                    <h4>{project.title}</h4>
                    <!-- <p>auto-updating map of my bike rides</p> -->
                    <div class="links">
                        <a href={project.source}>source </a>{#if project.link} // <a href={project.link}>site</a>{/if}
                    </div>
                </div>
            {/if}
            
        </div>
    {/each}
</div>

<style>
   .programming {
    display: grid;
    grid-template-columns: 1fr;
    margin: 1em;
    gap: 1em;
    overflow-y: scroll;
   }
   .project {
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    gap: 1em;
   }
   h4 {
    font-size: 1.6em;
    text-decoration: underline;
   }
   p {
    font-size: 0.8em;
   }
    a {
        text-decoration: underline;
        text-decoration-color: transparent;
        color: var(--text-secondary);
        transition: 0.25s ease-in-out;
        text-decoration-thickness: 0.1em;
        
    }
    .left {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-end;
        margin: 0;
        padding: 0;
        gap: 0;
    }

    .right {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
        margin: 0;
        padding: 0;
        gap: 0;
    }

    .links {
        font-size: 0.8em;
    }

    a:hover {
        text-decoration-color: var(--text-secondary);
        
    }

    img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        border-radius: 1em;
        transition: 0.25s ease-in-out;
    }

    img:hover {
        /* filter: brightness(0.8); */
        transform: scale(1.05);
        /* cursor: pointer; */
    }
</style>