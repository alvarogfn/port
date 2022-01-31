<script>
  import { onMount } from "svelte";
  import Project from "./Project.svelte";
  import Broken from "./utils/Broken.svelte";
  import Loading from "./utils/Loading.svelte";

  onMount(async () => {});

  async function getProjects() {
    const response = await fetch("http://localhost:8080/projects");
    // if (response.status !== 200) throw new Error("oi");
    const body = await response.json();
    return body;
  }

  let get = getProjects();
</script>

<section>
  <p>
    Eu amo desenvolver softwares, e ver meu trabalho ajudar é uma sensação
    incrível!
  </p>
  <section>
    {#await get}
      <Loading />
    {:then projects}
      <ul>
        {#each projects as project, i}
          <li>
            <Project {...project} />
          </li>
        {/each}
      </ul>
    {:catch error}
      <Broken />
    {/await}
  </section>
</section>

<style lang="scss">
  @use "../utils.scss" as *;
  p {
    font-style: italic;
    text-align: right;
    font-size: px-to-rem(14px);
    margin: 15px 5px 25px;
  }

  ul {
    display: flex;
    flex-flow: column nowrap;
    row-gap: 1.5rem;
  }
</style>
