<script>
  import CharacterItem from "./CharacterItem.svelte";
  export let items = [];
</script>

<style>
  .cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 1rem;
  }
  @media (max-width: 800px) {
    .cards {
      grid-template-columns: repeat(2, 1fr);
    }
  }
  @media (max-width: 500px) {
    .cards {
      grid-template-columns: 1fr;
    }
  }
</style>

<section class="cards">
  {#each items as item (item.char_id)}
    <CharacterItem {item} />
  {/each}
</section>
