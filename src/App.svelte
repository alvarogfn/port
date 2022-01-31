<script>
  import Aboutme from "./lib/Aboutme.svelte";
  import Header from "./lib/Header.svelte";
  import Contactme from "./lib/Contactme.svelte";
  import Projects from "./lib/Projects.svelte";
  import Separator from "./lib/utils/Separator.svelte";
  import Credits from "./lib/utils/Credits.svelte";
</script>

<div>
  <Header />
  <Separator />
  <main class="main">
    <Aboutme />
    <Separator />
    <Projects />
  </main>
  <footer class="footer">
    <Contactme />
    <Credits />
  </footer>
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

  .main {
    width: calc(100% - 30px);
    margin: 0 auto;
  }

  .footer {
    margin-top: 2rem;
    padding-top: 2rem;
    background-color: var(--white);
    color: var(--black);
  }
</style>
