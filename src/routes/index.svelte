<script lang="ts">
  import { store as AuthStore } from "../frontend/AuthProvider";
  import LoginForm from "../frontend/LoginForm.svelte";
</script>

<svelte:head>
  <title>Broken Session Management Demo</title>
</svelte:head>

{#if $AuthStore}
  <h1>Great success!</h1>
  <p>
    Logged in as <span>{$AuthStore}</span>
  </p>
  <button
    class="btn btn-outline btn-info"
    on:click={() =>
      prompt("Your session token", sessionStorage.getItem("session"))}
    >Reveal session token</button
  >
{:else}
  <LoginForm />
{/if}

<style>
  h1,
  p {
    text-align: center;
    margin: 0 auto;
  }

  h1 {
    font-size: 2.8em;
    text-transform: uppercase;
    font-weight: 700;
    margin: 0 0 0.5em 0;
  }

  p {
    margin: 1em auto;
  }

  @media (min-width: 480px) {
    h1 {
      font-size: 4em;
    }
  }
</style>
