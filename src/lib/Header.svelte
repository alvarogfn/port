<script>
  import Name from "./Name.svelte";
  import myPhoto from "../assets/my-photo.jpg";
</script>

<header>
  <img src={myPhoto} alt="Uma foto minha" srcset="" />
  <Name />
</header>

<style lang="scss">
  header {
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-flow: column nowrap;
    padding: 3rem 1rem 1rem 1rem;
    row-gap: 1.5rem;
  }
  img {
    width: 200px;
    box-shadow: 0 0 0 7px var(--black), 0 0 0 10px var(--white);
  }
</style>
