<script>
  import { onMount } from "svelte";
  import LogoSikje from "./LogoSikje.svelte";
  export let titel = "";

//   onMount(() => {
//     const interval = setInterval(() => {
//       console.log("beep (Block component)");
//     }, 1000);

//     return () => clearInterval(interval);
//   });
</script>

<h1>{titel}</h1>

<LogoSikje />
