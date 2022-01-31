<script>
  import Aboutme from "./lib/Aboutme.svelte";
  import Header from "./lib/Header.svelte";
  import Projects from "./lib/Projects.svelte";
  import Separator from "./lib/Separator.svelte";
</script>

<div class="container">
  <Header />
  <Separator />
  <main>
    <Aboutme />
    <Separator />
    <Projects />
  </main>
</div>

<style lang="scss" global>

  :root {
    --white: #f2f2f2;
    --black: #262626;
  }

  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }

  body {
    background-color: var(--black);
    color: var(--white);
    font-family: Ubuntu;
  }

  img {
    width: 100%;
  }

  ul,
  li,
  ol {
    list-style: none;
  }

  a {
    text-decoration: none;
    color: inherit;
  }

  .container {
    width: calc(100% - 15px);
    margin: 0 auto;
  }
</style>
