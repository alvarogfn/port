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
  <p>
    Eu amo desenvolver softwares, e ver meu trabalho ajudar é uma sensação
    incrível!
  </p>
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
    row-gap: 2rem;
  }

  .container {
    width: calc(100% - 15px);
    margin: 0 auto;
  }

  @media screen and (min-width: 744px) {
    .container {
      margin-top: 30px;
      min-width: 700px;

      width: calc(100% - 50px);
    }

    p {
      font-size: px-to-rem(18px);
    }

    ul {
      min-width: 600px;
      width: calc(80%);
      margin: 0 auto;
      row-gap: 3.2rem;
    }
  }

  @media screen and (min-width: 1080px) {
    .container {
      min-width: 670px;
      width: 1200px;
    }

    ul {
      margin-top: 50px;
      row-gap: 5rem;
    }
  }
</style>
