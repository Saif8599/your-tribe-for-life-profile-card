<script>
  export let className = "";

  import EmailIcon from "$lib/assets/icons/EmailIcon.svelte";
  import EmailHoverIcon from "$lib/assets/icons/EmailHoverIcon.svelte";
  import DiscordIcon from "$lib/assets/icons/DiscordIcon.svelte";
  import DiscordHoverIcon from "$lib/assets/icons/DiscordHoverIcon.svelte";
  import TwitterIcon from "$lib/assets/icons/TwitterIcon.svelte";
  import TwitterHoverIcon from "$lib/assets/icons/TwitterHoverIcon.svelte";
  // import GithubIcon from "$lib/assets/icons/GithubIcon.svelte";
  // import GithubHoverIcon from "$lib/assets/icons/GithubHoverIcon.svelte";
</script>

<section class="container {className}">
  <ul class="icon-list">
    <li class="icon-wrapper">
      <a href="mailto:SaifzMuhamad@gmail.com">
        <EmailIcon className="default-icon" />
        <EmailHoverIcon className="hover-icon" />
      </a>
    </li>
    <li class="icon-wrapper">
      <a href="/">
        <DiscordIcon className="default-icon" />
        <DiscordHoverIcon className="hover-icon" />
      </a>
    </li>
    <li class="icon-wrapper">
      <a href="/">
        <TwitterIcon className="default-icon" />
        <TwitterHoverIcon className="hover-icon" />
      </a>
    </li>
    <!-- <li class="icon-wrapper">
      <GithubIcon className="default-icon" />
      <GithubHoverIcon className="hover-icon" />
    </li> -->
  </ul>
</section>

<style>
  .container {
    width: fit-content;
  }

  .icon-list {
    list-style-type: none;
    margin: 0;
    padding: 0;
    width: fit-content;
  }

  .icon-wrapper {
    position: relative;
    display: inline-block;
    width: 50px;
    height: 50px;
    cursor: pointer;
  }

  .icon-wrapper :global(.default-icon),
  .icon-wrapper :global(.hover-icon) {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    transition: opacity 0.2s ease;
  }

  .icon-wrapper :global(.hover-icon) {
    opacity: 0;
  }

  .icon-wrapper:hover :global(.hover-icon) {
    opacity: 1;
  }
</style>
