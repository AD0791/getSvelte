<script>
  import Library from "./library/Library.svelte";
  import Detail from "./detail/Detail.svelte";
  //know what book is selected
  // temporary routing
  let page = "library";
  let pageArgs = {};
  function handleBookSelect(event) {
    page = "detail";
    pageArgs = event.detail;
  }
</script>

<style>
  main {
    padding: var(--spacingLarge);
  }
</style>

<main>
  {#if page === 'detail'}
    <Detail {...pageArgs} />
  {:else}
    <Library on:book-select={handleBookSelect} />
  {/if}
</main>
