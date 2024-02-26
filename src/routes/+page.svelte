<script lang="ts">
	import FlashCard from "$lib/components/FlashCard.svelte";

  let cards = [
    { front: "front 1", back: "back 1" },
    { front: "front 2", back: "back 2" },
    { front: "front 3", back: "back 3" },
    { front: "front 4", back: "back 4" },
    { front: "front 5", back: "back 5" },
    { front: "front 6", back: "back 6" },
    { front: "front 7", back: "back 7" },
    { front: "front 8", back: "back 8" },
    { front: "front 9", back: "back 9" },
    { front: "front 10", back: "back 10" },
    { front: "front 11", back: "back 11" },
    { front: "front 12", back: "back 12" },
    { front: "front 13", back: "back 13" },
    { front: "front 14", back: "back 14" },
    { front: "front 15", back: "back 15" },
    { front: "front 16", back: "back 16" },
    { front: "front 17", back: "back 17" },
    { front: "front 18", back: "back 18" },
    { front: "front 19", back: "back 19" },
    { front: "front 20", back: "back 20" },
    { front: "front 21", back: "back 21" },
    { front: "front 22", back: "back 22" },
    { front: "front 23", back: "back 23" },
    { front: "front 24", back: "back 24" },
    { front: "front 25", back: "back 25" },
  ];
</script>
<h1>Design Flash Cards</h1>

<main>
  {#each cards as { front, back }, index (index)}
    <FlashCard {front} {back} />
  {/each}
</main>


<style lang="scss">
  main {
    display: flex;
    flex-direction: column;
    height: 90vh;
    overflow-y: auto;
    scroll-snap-type: y mandatory;
    scroll-behavior: smooth;
    margin: 2rem;

    &::-webkit-scrollbar {
      display: none;
    }
  }
</style>