<script lang="ts">
  import favicon from "$lib/assets/favicon.svg";
  import { page } from "$app/stores";

  let { children } = $props();
</script>

<svelte:head>
  <link rel="icon" href={favicon} />
</svelte:head>

<nav>
  <a href="/" class:active={$page.url.pathname === "/"}>Home</a>
  <a href="/about" class:active={$page.url.pathname === "/about"}>About</a>
  <a href="/settings" class:active={$page.url.pathname === "/settings"}
    >Settings</a
  >
</nav>

{@render children?.()}

<style>
  nav {
	display: flex;
    gap: 1em;
  }
  a {
    color: black;
    text-decoration: none;
    font-size: 2em;
    font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS",
      sans-serif;
  }

  a.active {
    color: yellow;
    font-weight: 600;
  }
</style>
