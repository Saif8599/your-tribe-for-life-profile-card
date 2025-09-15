<script lang="ts">
  import logoSikje from "$lib/assets/logoSikje.svg";

  let { children } = $props();
</script>

<svelte:head>
  <link rel="icon" href={logoSikje} />
</svelte:head>

{@render children?.()}
