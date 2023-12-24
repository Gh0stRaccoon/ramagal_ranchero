<script>
  import { onDestroy, onMount } from "svelte";
  import MenuIcon from "../assets/icons/menu.svelte";
  let menuOpen = false;

  const handleClickOutside = (event) => {
    if (event.target.closest(".menu") || event.target.closest(".menu-button")) {
      return;
    }
    menuOpen = false;
  };

  onDestroy(() => {
    window.removeEventListener("click", handleClickOutside);
  });

  onMount(() => {
    window.addEventListener("click", handleClickOutside);
  });
</script>

<nav>
  <div class="text-logo">
    <h1>RAMAGAL</h1>
  </div>
  <button
    class="menu-button"
    on:click|stopPropagation={() => (menuOpen = !menuOpen)}
  >
    <MenuIcon height={40} width={40} />
  </button>
  <div class="menu" class:active={menuOpen}>
    <ul>
      <li><a href="#">Inicio</a></li>
      <li><a href="#servicios">Servicios</a></li>
      <li><a href="#">Contacto</a></li>
    </ul>
  </div>
</nav>

<style>
  nav {
    box-sizing: border-box;
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    padding: 0 1rem;
    height: 10dvh;
    background: transparent;
    position: fixed;
    top: 0;
    left: 50%;
    z-index: 1;
    transform: translateX(-50%);
  }
  .text-logo {
    font-size: 1.5rem;
    font-weight: 700;
    color: #ffffff99;
    -webkit-text-stroke: 1px #705638;
    filter: drop-shadow(0 0 4px #e1be95);
    mix-blend-mode: color;
    font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  }
  .text-logo h1 {
    margin: 0;
  }
  .menu-button {
    font-size: 1.5rem;
    font-weight: 700;
    color: #dcdcdc;
    background: none;
    border: none;
    display: flex;
    padding: 0;
  }
  .menu {
    position: absolute;
    top: 0;
    left: -100%;
    transition: left 0.25s ease-in-out;
    width: 50%;
  }

  .menu:global(.active) {
    left: 0;
  }

  .menu ul {
    display: flex;
    flex-direction: column;
    list-style: none;
    padding: 0;
    margin: 0;
  }
  .menu ul li a {
    font-size: 1rem;
    font-weight: 700;
    color: #ffffff;
    text-decoration: none;
    text-transform: uppercase;
    transition: all 0.25s ease-in-out;
    padding: 1rem 2rem;
    background-color: #705638;
    width: 100%;
    display: block;
  }
  .menu ul li a:hover {
    color: #e1be95;
  }

  @media (width > 768px) {
    .menu-button {
      display: none;
    }
    .menu {
      display: block;
      position: static;
      width: fit-content;
      top: 0;
      bottom: 0;
      left: 0;
      right: 0;
    }
    .menu ul {
      flex-direction: row;
    }
    .menu ul li a {
      margin: 0;
      width: auto;
      background: none;
    }
  }
</style>
