<script>
  import SocialMediaBlock from "$lib/components/SocialMediaBlock.svelte";
</script>

<dialog id="profile-card" class="profile-card" popover>
  dit is een dialog popover
  <!-- <SocialMediaBlock /> -->
</dialog>
<button class="dialog-button" popovertarget="profile-card">Click</button>

<style>
  .profile-card {
    position: fixed;
    margin: auto;
    padding: 2rem;
    max-width: 350px;
    width: 100%;
    border: 1px solid black;
    height: 80vh;
  }

  .profile-card:popover-open ~ .dialog-button {
    display: none;
  }

  .dialog-button {
    position: fixed;
    margin: auto;
    padding: 0;
    bottom: 10%;
    right: 45%;
    text-decoration: underline;
    background-color: transparent;
    border: none;
    cursor: pointer;
    font-size: var(--font-size-mobile-l);
  }

  @media (min-width: 765px) {
    .profile-card {
      max-width: 450px;
      right: 35%;
    }
    .dialog-button {
      font-size: var(--font-size-mobile-xl);
      right: 45%;
    }
  }

  @media (min-width: 1024px) {
    .profile-card {
      max-width: 550px;
      right: 5%;
    }
  }

  @media (min-width: 1440px) {
    .profile-card {
      max-width: 600px;
    }
    .dialog-button {
      font-size: var(--font-size-desktop-l);
      right: 30%;
      bottom: 20%;
    }
  }
</style>
