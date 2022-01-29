<script>
</script>

<div>
  <h1>Álvaro Guimarães</h1>
  <p>Front-End Developer</p>
</div>

<style lang="scss">
  @use "../utils.scss" as *;

  div {
    color: var(--white);
    display: flex;
    flex-flow: column nowrap;

    h1 {
      font-family: "Ubuntu mono", "ubuntu", "Roboto", sans-serif;
      font-size: px-to-rem(36px);
      text-align: center;
    }

    p {
      font-weight: 300;
      font-size: px-to-rem(18px);
    }
  }
</style>
