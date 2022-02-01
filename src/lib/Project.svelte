<script>
  import breakLink from "../assets/break.svg";

  export let name;
  export let description;
  export let img = breakLink;
  export let framework;
  export let repo;
  export let website;
</script>

<div class="container">
  <header>
    <h1>{name}</h1>
  </header>
  <main>
    <p>{description}</p>
    <img src={img} alt={name} />
  </main>
  <footer>
    <nav>
      <ul>
        <li><span class="framework">{framework}</span></li>
        <li><a class="code" href={repo}>código</a></li>
        <li><a class="website" href={website}>website</a></li>
      </ul>
    </nav>
  </footer>
</div>

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

    height: calc(125px + 22.5vw);
    width: 100%;

    border: 5px solid var(--white);
    box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);

    &:hover,
    &:active {
      scale: 1.1;
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
</style>
