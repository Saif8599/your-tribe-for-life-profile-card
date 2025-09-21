<script>
  import SocialMediaBlock from "$lib/components/SocialMediaBlock.svelte";
</script>

<dialog id="profile-card" class="profile-card" popover>
  <div class="carousel carousel--scroll-buttons carousel--scroll-markers">
    <li class="carousel-slide">
      <!-- Fallback -->
      <img
        src="src\lib\assets\images\Character-1.png"
        alt="Character-2"
        loading="lazy"
        class="character-1"
      />
    </li>
    <li class="carousel-slide">
      <!-- Fallback -->
      <img
        src="src\lib\assets\images\Character-2.png"
        alt="Character-2"
        loading="lazy"
        class="character-2"
      />
    </li>
    <li class="carousel-slide">
      <!-- Fallback -->
      <img
        src="src\lib\assets\images\Character-3.png"
        alt="Character-3"
        loading="lazy"
        class="character-3"
      />
    </li>
  </div>

  <!-- <SocialMediaBlock /> -->
</dialog>
<button class="dialog-button" popovertarget="profile-card">Click</button>

<style>
  /* Profile card */
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

  /* Carousel */

  .carousel {
    display: flex;
    width: 100%;
    overflow-x: auto;
    overscroll-behavior-x: contain;
    scroll-snap-type: x mandatory;
    scroll-behavior: smooth;
    anchor-name: --carousel;
    text-align: center;
    scroll-marker-group: after;
  }
  .carousel-slide {
    flex: 0 0 100%;
    scroll-snap-align: center;
  }

  .carousel--scroll-buttons {
    &::scroll-button(*) {
      position: fixed;
      position-anchor: --carousel;
      cursor: pointer;
      border: none;
      background-color: transparent;
    }

    &::scroll-button(right) {
      position-area: inline-end center;
      content: url(../assets/icons/ArrowRight.svg);
      translate: -100%;
    }
    &::scroll-button(right):disabled {
      opacity: 0;
    }

    &::scroll-button(left) {
      position-area: inline-start center;
      content: url(../assets/icons/ArrowLeft.svg);
      translate: 100%;
    }
    &::scroll-button(left):disabled {
      opacity: 0;
    }
  }

  .carousel::scroll-marker-group {
    display: flex;
    justify-content: center;
    gap: 0.5em;
  }

  .carousel-slide::scroll-marker {
    content: "";
    height: 10px;
    width: 10px;
    border-radius: 50%;
    border: 1px solid var(--text-color);
  }

  .carousel-slide::scroll-marker:target-current {
    background-color: var(--text-color);
  }

  ::-webkit-scrollbar {
    width: 0;
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

  /* Media query */

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
