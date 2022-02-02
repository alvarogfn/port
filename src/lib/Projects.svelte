<script>
  import Project from "./Project.svelte";
  import Broken from "./utils/Broken.svelte";
  import Loading from "./utils/Loading.svelte";

  async function getProjects() {
    const response = await fetch("http://192.168.0.120:8080/projects");
    // if (response.status !== 200) throw new Error("oi");
    const body = await response.json();
    return body;
  }

  let get = getProjects();
</script>

<section class="container">
  <section>
    {#await get}
      <Loading />
    {:then projects}
      <ul>
        {#each projects as project}
          <li>
            <Project {...project} />
          </li>
        {/each}
      </ul>
    {:catch error}
      <Broken />
    {/await}
    <p>
      Eu amo desenvolver softwares, e ver meu trabalho ajudar é uma sensação
      incrível!
    </p>
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
    display: grid;

    grid-template-columns: repeat(auto-fit, minmax(300px, 400px));
    grid-auto-rows: 450px;

    align-items: center;
    justify-content: space-around;

    gap: 2rem;
    margin: 0 auto;

    min-width: 320px;
    width: 100%;
  }

  .container {
    width: calc(100% - 15px);
    margin: 0 auto;
  }

  @media screen and (min-width: 744px) {
    ul {
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 2.25rem;
    }
    p {
      font-size: px-to-rem(18px);
    }
  }

  @media screen and (min-width: 1080px) {
    ul {
      grid-template-columns: repeat(auto-fit, minmax(350px, 420px));
      gap: 3rem;
    }
  }
</style>
