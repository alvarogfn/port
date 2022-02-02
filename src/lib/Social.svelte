<script>
  let app = ["linkedin", "github", "whatsapp"];
  let link = {
    linkedin: "https://www.linkedin.com/in/alvarogfn/",
    github: "https://github.com/alvarogfn/",
    whatsapp: "https://api.WhatsApp.com/send?phone=5538998056168",
  };
</script>

<nav>
  <ul>
    {#each app as social}
      <li>
        <a
          target="_blank"
          rel="norefferer noopener"
          class={social}
          href={link[social]}>{social}</a
        >
      </li>
    {/each}
  </ul>
</nav>

<style lang="scss">
  ul {
    flex-flow: row nowrap;
    justify-content: space-evenly;
    display: flex;

    margin: 1rem 0;
  }

  li {
    width: 40px;
    height: 40px;

    display: flex;
    align-items: center;
    justify-content: center;
  }

  a {
    width: 100%;
    height: 100%;
    text-indent: -300000px;

    cursor: pointer;

    background-size: cover;
    border-radius: 3px;
  }

  .whatsapp {
    background-image: url("../assets/whatsapp.svg");
  }

  .linkedin {
    background-image: url("../assets/linkedin.svg");
  }

  .github {
    background-image: url("../assets/github.svg");
  }

  @media screen and (min-width: 744px) {
    ul {
      width: 30%;
      margin: 0 auto;
    }
  }
</style>
