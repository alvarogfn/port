<section>
  <p class="p-italic">Um pouco sobre mim...</p>
  <p>
    Olá, meu nome é <strong>Álvaro Guimarães</strong>, sou um estudante de
    <strong>Sistemas de Informação</strong> pela <strong>UniAtenas</strong> e
    tenho como objetivo ingressar no mercado como
    <strong>front-end Developer</strong>.
  </p>
  <p>
    Sou uma pessoa <strong>curiosa</strong>, <strong>criativa</strong>,
    <strong>dedicada</strong>
    e com vontade de <strong>melhorar a cada dia mais</strong>. Sempre à busca
    de <strong>novas tecnologias</strong> e novos meios de
    <strong>resolver problemas</strong>.
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
</style>
