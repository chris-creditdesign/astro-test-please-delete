<script>
  import { onMount } from "svelte";
  import { SimpleButton } from "nature-immersive-svelte-components";
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

<h3>{randomMessage}!</h3>

{#if mounted}
  <SimpleButton
    message="Click to change greeting"
    on:click={() => getRandomMessage()}
  />
{/if}
