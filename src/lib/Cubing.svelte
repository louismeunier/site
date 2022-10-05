<script lang="ts">
    // import cubing from "../data/cubing.csv?raw";
  
    const splitCsv = cubing.split(/\n/)
    const cubingData = splitCsv.splice(1).map((row) => {
      const [name, link, description] = row.split(",");
      return { name, link, description };
    });
</script>

<ul>
    {#each cubingData as line}
        <li>
          <a title={line.description} class="external" href={line.link} target="_blank">
            {line.name}
          </a>
        </li>
    {/each}
</ul>
<p>You can also access the raw unformatted spreadsheet <a class="external" href="update_this_when_uploaded" target="_blank">here.</a></p>

<style>
    ul {
        display: grid;
        width: 50%;
        /* make 2 even columns unless screen too small */
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
        gap: 1.5em;
    }
</style>