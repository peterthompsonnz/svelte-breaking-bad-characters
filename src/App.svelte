<script>
  import { onMount } from "svelte";
  import Header from "./Header.svelte";
  import CharacterGrid from "./CharacterGrid.svelte";
  import Spinner from "./Spinner.svelte";
  import Search from "./Search.svelte";

  let items = [];
  let isLoading = true;
  let query = "";

  async function fetchItems(query) {
    const result = await fetch(
      `https://www.breakingbadapi.com/api/characters?name=${query}`
    );
    const json = await result.json();
    items = json;
    isLoading = false;
  }

  onMount(() => {
    fetchItems(query);
  });

  function onNotify(evt) {
    query = evt.detail;
    fetchItems(query);
  }
</script>

<style>
  .container {
    max-width: 1100px;
    margin: auto;
    padding: 0 20px;
  }
</style>

<div class="container">
  <Header />
  <Search on:notify={onNotify} />
  {#if isLoading}
    <Spinner />
  {:else}
    <CharacterGrid {items} />
  {/if}
</div>
