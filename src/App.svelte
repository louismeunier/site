<script lang="ts">
  import { onMount } from 'svelte';

  let ready = false;
  onMount(() => ready = true);
  const sections = [
    // {
    //   title: "speedcubing",
    //   description: `I've been speedcubing "competitively" for about ${new Date().getFullYear() - 2015} years, and organizing WCA competitions for about ${new Date().getFullYear() - 2019}. While I'm  no expert at either, I've collected quite a list of resources and tools over time:`,
    //   component: Cubing
    // },
    {
      title: "programming",
      description: `I've been programming for ${new Date().getFullYear()-2020} years, and listed here are some of the rare projects I'm proud of.`
    },
    {
      title: "notes",
      description: "A number of notes from different courses I've taken, mostly for my own reference, but maybe someone will find them useful."
    }
  ]
  import { fly } from "svelte/transition";
    import Programming from './lib/Programming.svelte';
    import About from './lib/About.svelte';
  let currentPage:"programming"|"notes"|"about"= null; 
</script>

<div class="wrapper">
  {#if ready}
    <main>
      <div class="toc">
      <h1 in:fly={{x: -500, duration: 500}}>louis meunier</h1>
      <div class="contents">
        <a 
          in:fly={{x: -500, duration: 650}}  
          class={`${currentPage === "about" ? "active" : ""}`}
          on:click={() => {currentPage == "about" ? currentPage = null : currentPage = "about"}}
          href="#"
          >
            <h2>about</h2>
      </a>
        <a 
          in:fly={{x: -500, duration: 800}}  
          class={`${currentPage === "programming" ? "active" : ""}`}
          on:click={() => {currentPage == "programming" ? currentPage = null : currentPage = "programming"}}
          href="#"
          >
            <h2>programming</h2>
      </a>
      <a 
        in:fly={{x: -500, duration: 900}} 
        target="_blank"
        href="http://notes.louismeunier.net">
        <h2>notes</h2>
      </a>
      </div>
      <div class="contents">
        <a in:fly={{x: -500, duration: 1100}} class="external" target="_blank" href="https://github.com/louismeunier">
          <h2>github</h2>
        </a>
        <a in:fly={{x: -500, duration: 1200}} class="external" target="_blank" href="https://www.linkedin.com/in/louis-meunier-112b55203/">
          <h2>linkedin</h2>
        </a>
      </div>
    </div>
    <div class="display" >
      {#if currentPage === "programming"}
        <Programming/>
      {:else if currentPage === "about"}
        <About/>
      {/if}
    </div>
  </main>
  <footer in:fly={{x:-500, duration: 1300}}>
    <span>(c) 2022, Louis Meunier</span>
  </footer>
  {/if}
</div>

<style>
  .wrapper {
    display: flex;
    flex-direction: column;
    height: 100vh;
    gap: 5em;
    padding: 0;
    margin: 0;
  }

  main {
    flex-grow: 1;
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  .toc {
    /* margin-left: 1rem; */
    overflow: hidden;
  }

  .toc > * {
    margin-left: 1rem;
  }

  .contents {
    display: flex;
    gap: 0.8em;
    flex-direction: column;
    margin-top: 3rem;
    align-items: flex-start;
    justify-items: flex-start;
  }

  .contents h2 {
    margin-bottom: 0;
  }

  h1 {
    font-size: 2.4rem;
    transition: 1s ease-in-out;
  }

  h2 {
    font-size: 2.2rem;
    /* transition: 1s ease-in-out; */
  }

  a {
    color: var(--text-primary);
    text-decoration: underline;
    text-decoration-color: transparent;
    text-underline-offset: 0.15em;
    text-decoration-thickness: 0.15em;
    transition: 0.25s ease-in-out;
  }

  a:hover {
    text-decoration-color: var(--text-secondary);
  }

  a.external {
    color: var(--text-secondary);
  }

  a.external:visited {
    color: var(--text-secondary);
  }

  a.active {
   color: var(--text-tertiary);
   text-decoration-color: var(--text-tertiary);
  }

  footer {
    width: 100vw;
    text-align: center;
    color: var(--text-tertiary)
  }
  
  span {
    font-size: 0.8rem;
  }

  .temp {height: 50vh;}

  .display {
    /* position: absolute; */
    /* overflow-y: scroll; */
  }
</style>