<script>
  import { onMount } from "svelte";
  export let messages = ["test"];

  let mounted = false;
  let randomMessage = messages[0];

  const getRandomMessage = () => {
    randomMessage = messages[Math.floor(Math.random() * messages.length)];
  };

  onMount(() => {
    mounted = true;
  });
</script>

<h3>Hello {randomMessage}!</h3>

{#if mounted}
  <button on:click={() => getRandomMessage()}>Change message</button>
{/if}
