<script lang="ts">
  export let front: string = "Front of the card";
  export let back: string = "Back of the card";

  let isFlipped: boolean = false;

  function handleClick(): void {
    isFlipped = !isFlipped;
  }

  function handleKeydown(event: KeyboardEvent): void {
    if (event.key === "Enter") {
      isFlipped = !isFlipped;
    }
  }
</script>

<div role="button" tabindex="0" class="flashcard" on:click={handleClick} on:keydown={handleKeydown}>
  <div class="card" style={`transform: rotateY(${isFlipped ? 180 : 0}deg)`}>
    <div class="front">
      {front}
    </div>
    <div class="back">
      {back}
    </div>
  </div>
</div>

<style lang="scss">
  .flashcard {
    width: 100%;
    height: 80vh;
    perspective: 1000px;
    flex: 0 0 auto;
    scroll-snap-align: start;
    margin: 16px auto;

    .card {
      width: 100%;
      height: 100%;
      transform-style: preserve-3d;
      transition: transform 0.5s;

      .front,
      .back {
        position: absolute;
        width: 100%;
        height: 100%;
        backface-visibility: hidden;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 18px;
        background-color: #f0f0f0;
        border: 1px solid #ccc;
        border-radius: 8px;
      }

      .back {
        transform: rotateY(180deg);
      }
    }
  }
</style>
