<!-- Home Page -->
<script lang="ts">
  import '../app.css';
  import { Deck, Player } from '../Types.svelte';
  import Card from './Card.svelte';

  let gameStarted = false;
  const player = new Player('Player 1');

  const startGame = () => {
    gameStarted = true;
    const deck = new Deck();
    deck.shuffle();
    player.clearHand();
    player.receiveCard(deck.deal());
    player.receiveCard(deck.deal());
		userHand = getUserHand();
		console.log(userHand);
  };

  $: userHand = gameStarted ? getUserHand() : null;

  function getUserHand() {
    return player.getHand(); // Assuming getHand() returns an array of cards
  }
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<h1 class="text-center text-4xl my-5">Pre-Flop Equity</h1>
	<div class="flex flex-col">
		<button class="mx-auto mb-[2rem] btn glass w-1/12 flex justify-center" on:click={startGame}>Generate Hand</button>
		<div class="flex flex-row">
			{#if userHand}
			{#each userHand as card}
			<Card {card} />
			{/each}
			{/if}
		</div>
	</div>
</section>
