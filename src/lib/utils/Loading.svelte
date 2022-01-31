<p>Carregando</p>

<style lang="scss">
  @keyframes loading {
    0% {
      transform: translate(-50%, -50%) rotate(0deg);
    }
    25% {
      transform: translate(-50%, -50%) rotate(45deg);
    }
    50% {
      transform: translate(-50%, -50%) rotate(45deg);
    }
    100% {
      transform: translate(-50%, -50%) rotate(90deg);
    }
  }

  @keyframes typewriter {
    0% {
      content: ".";
    }
    50% {
      content: "..";
    }
    100% {
      content: "...";
    }
  }

  p {
    position: relative;
    width: min-content;
    display: flex;
    align-items: flex-end;
    padding: 0.3rem;

    margin: 0 auto;

    height: 70px;

    font-style: italic;

    &::before {
      position: absolute;
      content: "";
      display: block;

      width: 25px;
      height: 25px;
      background-color: var(--white);

      animation: loading 1s infinite ease-in-out;
      top: 35%;
      left: 50%;
    }
    &::after {
      content: "";
      animation: typewriter 2s infinite linear;
    }
  }
</style>
