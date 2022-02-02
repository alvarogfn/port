<script>
  import Social from "./Social.svelte";
  let email = "Alvarogfn@protonmail.com";
</script>

<section class="emphase">
  <p>
    <strong>Contate-me</strong><br />
    para um trabalho de
    <strong>sucesso!</strong>
  </p>
</section>
<section class="email">
  <p>
    <a
      target="_blank"
      rel="norefferer noopener"
      href="mailto:alvarogfn@protonmail.com">{email}</a
    >
  </p>
</section>
<section>
  <Social />
</section>

<style lang="scss">
  @use "../utils.scss" as *;

  p {
    text-align: center;
  }

  .emphase {
    font-size: px-to-rem(15px);
    line-height: px-to-rem(26px);
    letter-spacing: 0.1rem;
    text-transform: uppercase;
  }

  .email {
    font-weight: bold;
    font-size: px-to-rem(18px);
    font-family: "Ubuntu", monospace;

    line-height: px-to-rem(18px);
    letter-spacing: 0.05rem;

    text-align: center;
    text-transform: uppercase;

    margin: 3rem 0;

    color: var(--black);
  }

  @media screen and (min-width: 744px) {
    .email {
      font-size: px-to-rem(22px);
    }
  }
</style>
