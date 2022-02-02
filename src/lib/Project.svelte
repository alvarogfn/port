<script>
  import breakLink from "../assets/break.svg";

  export let name;
  export let description;
  export let img = breakLink;
  export let framework = null;
  export let repo = null;
  export let website = null;
</script>

<section class="container">
  <h1>{name}</h1>
  <p>{description}</p>
  <img src={img} alt={name} />
  <nav>
    <ul>
      <li>
        {#if framework.url}
          <a
            href={framework.url}
            target="_blank"
            rel="norefferer noopener"
            class="framework">{framework.name}</a
          >
        {:else if framework.name}
          <span class="framework">{framework.name}</span>
        {:else}
          <span class="framework">Não informado</span>
        {/if}
      </li>
      <li>
        {#if repo}
          <a target="_blank" rel="norefferer noopener" class="code" href={repo}>
            código
          </a>
        {:else}
          <span class="code">código</span>
        {/if}
      </li>
      <li>
        {#if website}
          <a
            class="website"
            href={website}
            target="_blank"
            rel="norefferer noopener"
          >
            website
          </a>
        {:else}
          <span class="website">website</span>
        {/if}
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

    font-family: "Ubuntu Mono", monospace;
    font-weight: bold;
    font-size: px-to-rem(17px);
  }

  a,
  span {
    display: flex;
    align-items: center;
    justify-content: center;

    background-repeat: no-repeat;
    background-position: left center;
    background-size: 17px 17px;
    height: 30px;

    padding-left: 1.4rem;

    &.framework {
      background-image: url("../assets/framework.svg");
    }
    &.code {
      background-image: url("../assets/source.svg");
    }
    &.website {
      background-image: url("../assets/website.svg");
    }
  }

  a {
    cursor: pointer;

    transition: 200ms;
    color: var(--white);
    filter: brightness(0) invert(0.95);
    &:hover {
      scale: 1.05;
    }
  }
  span {
    filter: brightness(0) invert(1) opacity(0.5);
  }

  @media screen and (min-width: 744px) {
    .container {
      display: grid;
      grid-template-columns: 4fr 3fr;
      grid-template-rows: 70px minmax(50px, auto) 40px;
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

      min-width: 150px;
      min-height: 150px;

      width: 100%;
      height: 180px;

      max-height: 100%;
      max-width: 100%;

      align-self: center;
      justify-self: center;

      &:hover {
        object-fit: contain;
      }
    }
  }

  @media screen and (min-width: 1080px) {
    .container {
      grid-template-columns: 3fr 5fr;
      grid-template-rows: 1fr minmax(100px, auto) 1fr;
      column-gap: 3rem;
    }

    img {
      min-height: 350px;
    }
  }
</style>
