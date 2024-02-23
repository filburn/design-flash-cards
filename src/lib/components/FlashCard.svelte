<script lang="ts">
  export let front: string;
  export let back: string;

  function flipCard(card: Element): void {
    card.classList.toggle('flipped');
  }

  const cardElements: HTMLCollection = document.getElementsByClassName('card');
  Array.from(cardElements).forEach((c: Element) => {
    c.addEventListener('click', () => {
      flipCard(c);
    });
  });
</script>

<div class="flash-card">
  <div class="flash-card__front">
    {front}
  </div>
  <div class="flash-card__back">
    {back}
  </div>
</div>
