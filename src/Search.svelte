<script>
  import { createEventDispatcher } from "svelte";
  let text = "";

  const dispatch = createEventDispatcher();

  function onChange(q) {
    text = q;
    dispatch("notify", q);
  }
</script>

<style>
  .search {
    height: 100px;
  }
  input[type="text"] {
    display: block;
    padding: 10px;
    font-size: 20px;
    border: 0;
    border-radius: 5px;
    width: 60%;
    margin: auto;
  }
</style>

<section class="search">
  <div>
    <input
      type="text"
      placeholder="Search characters"
      bind:value={text}
      on:input={e => onChange(e.target.value)} />
  </div>
</section>
