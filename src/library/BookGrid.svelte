<script>
  import Heart from "./Heart.svelte";
  import BookCover from "../common/BookCover.svelte";
  export let books = [];
</script>

<style>
  /* your styles go here */
  ul {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(10rem, 1fr));
    grid-template-columns: repeat(auto-fill, minmax(8rem, 1fr));
    grid-auto-rows: 12.8rem;
    gap: var(--spacingMedium);
    list-style: none;
    max-width: 100%;
    padding: 0;
  }
  li {
    position: relative;
    display: flex;
  }
  .heart {
    position: absolute;
    bottom: calc(-1 * var(--spacingSmall));
    right: calc(-1 * var(--spacingSmall));
  }
</style>

<!-- markup (zero or more items) goes here -->
<ul>
  {#each books as book}
    <li>
      <BookCover {book} on:book-select />
      {#if book.favorite}
        <div class="heart">
          <Heart />
        </div>
      {/if}
    </li>
  {/each}
</ul>
