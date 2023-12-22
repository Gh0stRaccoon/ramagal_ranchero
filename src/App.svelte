<script>
  import video from "./assets/ramagal.webp";
  import Logo from "./assets/Logo.png";
  import Nav from "./components/Nav.svelte";
</script>

<main>
  <Nav />
  <header>
    <img class="video" src={video} alt="" />
    <div class="overlay"></div>
    <img class="logo" src={Logo} alt="" />
  </header>
</main>

<style>
  header {
    position: relative;
    height: 100vh;
    overflow: hidden;
  }
  .video {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: left;
    filter: contrast(1.2) brightness(0.8);
    position: inherit;
  }
  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: #33333377;
    mix-blend-mode: hard-light;
  }
  .logo {
    width: 70%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    animation:
      fade-in 2.5s ease-in-out forwards,
      bump 4s ease-in-out infinite 2.5s;
  }

  @keyframes fade-in {
    0% {
      opacity: 0;
      transform: translate(-50%, -50%) scale(0.5);
    }
    80% {
      opacity: 1;
      transform: translate(-50%, -50%) scale(1.2);
    }
    90% {
      opacity: 1;
      transform: translate(-50%, -50%) scale(1);
    }
  }

  @keyframes bump {
    0% {
      transform: translate(-50%, -50%) scale(1);
    }
    50% {
      transform: translate(-50%, -50%) scale(1.2);
    }
    100% {
      transform: translate(-50%, -50%) scale(1);
    }
  }

  @media (width > 768px) {
    .logo {
      width: 30%;
    }
  }
</style>
