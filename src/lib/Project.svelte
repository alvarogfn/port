<script>
  import breakLink from "../assets/break.svg";

  export let name;
  export let description;
  export let img = breakLink;
  export let framework;
  export let repo;
  export let website;
</script>

<section class="container">
  <h1>{name}</h1>
  <p>{description}</p>
  <img src={img} alt={name} />
  <nav>
    <ul>
      <li><span class="framework">{framework}</span></li>
      <li>
        <a target="_blank" rel="norefferer noopener" class="code" href={repo}
          >código</a
        >
      </li>
      <li>
        <a
          class="website"
          href={website}
          target="_blank"
          rel="norefferer noopener">website</a
        >
      </li>
    </ul>
  </nav>
</section>

<style lang="scss">
  @use "../utils.scss" as *;

  @keyframes changePic {
    to {
      filter: brightness(100%);
    }
  }

  .container {
    display: flex;
    flex-flow: column nowrap;
    row-gap: 0.5rem;
  }

  h1 {
    display: flex;
    align-items: center;
    padding-left: 35px;

    font-size: px-to-rem(16px);
    font-weight: bold;
    text-transform: uppercase;

    height: 40px;

    background-image: url("../assets/code.svg");
    background-repeat: no-repeat;
    background-position: left center;
    letter-spacing: 2px;
  }

  p {
    font-weight: 300;
    margin-bottom: 1rem;
  }

  img {
    object-fit: cover;

    transition: 200ms;

    min-height: 225px;
    height: 50vw;
    width: 100%;

    border: 5px solid var(--white);
    box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);

    &:hover,
    &:active {
      scale: 1.05;
    }
  }

  ul {
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
    align-items: center;
    column-gap: 0.5rem;
  }

  li {
    text-transform: uppercase;

    color: rgba($color: $white, $alpha: 0.5);

    font-family: "Ubuntu Mono", monospace;
    font-weight: bold;
    font-size: px-to-rem(17px);
  }

  a,
  span {
    cursor: pointer;

    display: flex;
    align-items: center;
    justify-content: center;

    height: 30px;

    padding-left: 1.3rem;

    background-repeat: no-repeat;
    background-position: left center;
    background-size: 17px 17px;

    &.framework {
      background-image: url("../assets/framework.svg");
    }
    &.code {
      background-image: url("../assets/source.svg");
    }
    &.website {
      background-image: url("../assets/website.svg");
    }

    transition: 200ms;

    &:hover {
      scale: 1.05;
    }
  }

  @media screen and (min-width: 744px) {
    .container {
      display: grid;
      grid-template-columns: 4fr 3fr;
      grid-template-rows: 70px 70px 40px;
      column-gap: 2rem;
    }

    h1 {
      grid-row: 1 / 2;
      grid-column: 1 / 2;
      align-self: end;
    }

    p {
      grid-column: 1 / 2;
      grid-row: 2 / 3;
      align-self: start;
    }

    nav {
      grid-column: 1 / 2;
      grid-row: 3 / 4;
    }

    img {
      grid-column: 2 / 3;
      grid-row: 1 / 4;

      height: 100%;
      min-height: initial;

      width: 100%;

      align-self: center;
      justify-self: center;


      &:hover {
        object-fit: contain;

      }
    }
  }
</style>
