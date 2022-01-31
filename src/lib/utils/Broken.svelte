<script>
  import src from "../../assets/fetch-break.svg";
</script>

<section>
  <img {src} alt="" />
  <p>
    Por favor tente reiniciar a pagina.
  </p>
</section>

<style lang="scss">
  @use "../../utils.scss" as *;

  @keyframes appear {
    from {
      transform: translateY(-20px);
      opacity: 0;
    }
    to {
      transform: translateY(0px);
      opacity: 1;
    }
  }

  p {
    font-family: "Ubuntu monospace", monospace;
    text-align: center;
    font-size: px-to-rem(12px);
  }

  section {
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
    justify-content: center;

    margin: 2rem auto;

    color: rgba($color: $white, $alpha: 0.5);

    animation: appear 200ms ease-in-out forwards;
  }

  img {
    width: 75px;
    fill: rgba($color: $white, $alpha: 0.5);
  }
</style>
