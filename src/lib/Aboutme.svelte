<section>
  <p class="p-italic">Um pouco sobre mim...</p>

  <p>Olá, tudo bem?</p>

  <p>
    Eu tive meu primeiro contato com a área de <strong>desenvolvimento</strong>
    na infância, em 2012 / 2013. Costumava passar meu tempo elaborando páginas de
    <strong>HTML/CSS</strong>
    para perfis em blogs e forums. E nessa mesma época, tive contato com a
    criação de
    <strong>chatbots em python</strong>.
  </p>
  <p>
    Sempre fiquei maravilhado ao ver como <strong>pequenas coisas</strong> podem
    <strong>se tornar</strong>
    coisas ainda maiores e <strong>fazer tanta diferença</strong> na vida das pessoas.
  </p>
  <p>
    Hoje, eu estudo as tecnologias <strong>React.js</strong>,
    <strong>Vue.js</strong>,
    <strong>Svelte</strong>, <strong>HTML5</strong>, <strong>CSS3</strong>,
    <strong>Dart</strong>
    e <strong>Flutter</strong>
    de forma autodidata e estou cursando <strong>Sistemas de Informação</strong>
    na UniAtenas.
  </p>

  <p>
    Meu <strong>objetivo</strong> para o próximo ano é conseguir ter meu
    <strong>primeiro estágio</strong>
    na área como <strong>front-end</strong> e avançar minha habilidade em
    <strong>inglês até a fluência</strong>.
  </p>
</section>

<style lang="scss">
  @use "../utils.scss" as *;

  .p-italic {
    font-family: "Ubuntu";
    font-style: italic;
    text-align: right;
  }

  section {
    display: flex;
    flex-flow: column nowrap;
    row-gap: 0.7rem;
    font-size: px-to-rem(15px);
    padding: 0 0.25rem;
  }

  p {
    font-weight: 300;
    line-height: px-to-rem(30px);
  }

  strong {
    font-family: "Ubuntu";
    font-weight: bold;
  }

  @media screen and (min-width: 744px) {
    p {
      font-size: px-to-rem(18px);
      margin: 0.5rem 0;
    }
    section {
      padding: 0 4rem;
    }
  }
</style>
