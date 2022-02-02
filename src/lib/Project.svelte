<script>
  import breakLink from "../assets/break.svg";

  export let name;
  export let description;
  export let img = breakLink;
  export let framework = null;
  export let repo = null;
  export let website = null;
</script>

<section>
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

  section {
    display: grid;
    grid-template-rows: 50px 100px 250px 50px;
    align-items: center;
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
    max-height: 130px;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  img {
    object-fit: cover;

    width: 100%;
    height: 100%;

    transition: 200ms;

    margin-bottom: 0.5rem;

    align-self: center;
    justify-self: center;

    border: 0.25rem solid var(--white);

    &:hover,
    &:active {
      scale: 1.05;
      object-fit: contain;
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

</style>
