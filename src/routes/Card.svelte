<script lang="ts">
  type Card = {
    rank: string;
    suit: string;
  };
  export let card: Card; // Define the 'card' prop
</script>

<div class="relative inline-block text-left">
  <button
    type="button"
    class="inline-flex justify-center md:w-[8rem] h-auto 3xs:w-[5rem] mx-1 rounded-md shadow-sm border border-gray-300 bg-white text-sm font-medium text-gray-700 hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
  >
    <img
      src={`src/lib/images/${card?.rank}${card?.suit}.svg`}
      alt={`${card?.rank}${card?.suit}`}
    />
  </button>

</div>
