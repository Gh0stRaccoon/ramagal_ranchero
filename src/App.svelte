<script>
  import video from "./assets/ramagal.webp";
  import Logo from "./assets/Logo.png";
  import Nav from "./components/Nav.svelte";
  import grupo_ramagal from "./assets/ramagal_grupo (1).png";
  import mezcladora from "./assets/mezcladora.png";
</script>

<Nav />
<header>
  <img class="video" src={video} alt="" />
  <div class="overlay"></div>
  <img class="logo" src={Logo} alt="" />
</header>
<main>
  <section id="servicios">
    <header>
      <h2>Servicios</h2>
      <p>
        Ofrecemos servicios de música en vivo para todo tipo de eventos, desde
        bodas, bautizos, cumpleaños, fiestas de fin de año, etc. Además,
        ofrecemos amplificación de sonido para distintos tipos de eventos.
      </p>
    </header>
    <ul>
      <li>
        <article class="service">
          <div class="img-container">
            <img src={grupo_ramagal} alt="" />
          </div>
          <div class="card-content">
            <h3>Música en vivo</h3>
            <p>
              Contamos con un amplio repertorio de música nacional e
              internacional, para que tu evento sea inolvidable.
            </p>
          </div>
        </article>
      </li>
      <li>
        <article class="service">
          <div class="img-container">
            <img src={grupo_ramagal} alt="" />
          </div>
          <div>
            <h3>Amplificación de sonido</h3>
            <p>
              Contamos con equipos de amplificación de sonido para diversos
              tipos de evento.
            </p>
          </div>
        </article>
      </li>
    </ul>
  </section>
  <section id="Contacto">
    <header>
      <h2>Contacto</h2>
      <p>
        Contactanos para más información sobre nuestros servicios, o para hacer
        una cotización a travez de este formulario.
      </p>
    </header>
    <form action="">
      <input type="text" placeholder="Nombre" />
      <input type="email" placeholder="Correo" />
      <input type="phone" placeholder="Teléfono" />
      <textarea name="" id="" cols="30" rows="10"></textarea>
      <input type="submit" value="Enviar" />
    </form>
  </section>
</main>

<style>
  header:not(main header) {
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
    color: rgb(112, 86, 56);
    background: linear-gradient(
      0deg,
      rgb(38, 29, 19) 2%,
      rgba(0, 0, 0, 0.2) 20%
    );
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

  main {
    padding: 1rem;
    background-color: rgb(38, 29, 19);
    color: rgb(220, 220, 220);
  }

  h2,
  p {
    margin: 0;
  }

  h2 {
    background-image: linear-gradient(
      to bottom,
      rgb(229, 175, 113) 0%,
      rgb(245, 218, 188) 50%,
      rgb(229, 175, 113) 100%
    );
    background-clip: text;
    -webkit-text-fill-color: transparent;
    font-size: xx-large;
  }

  h3 {
    font-size: x-large;
    margin: 0;
    margin-top: 1rem;
  }

  section {
    padding-top: 2rem;
    display: grid;
    gap: 1rem;
    scroll-margin-top: 3rem;
    font-size: 1.125rem;
    text-wrap: balance;
  }
  ul {
    display: grid;
    gap: 1rem;
    list-style: none;
    padding: 0;
    margin: 0;
  }
  article.service {
    display: grid;
    grid-template-columns: 1fr;
    align-items: center;
    justify-content: center;
    padding: 1rem;
    background: linear-gradient(
      to bottom,
      rgb(112, 86, 56) 0%,
      rgb(142, 123, 102) 100%
    );
    border-radius: 1rem;
    margin-top: 3rem;
  }

  article.service img {
    width: 100%;
    max-width: 320px;
    height: 200px;
    object-fit: cover;
    object-position: top;
    -webkit-mask-image: linear-gradient(to bottom, black 70%, transparent 85%);
    mask-image: linear-gradient(to bottom, black 70%, transparent 85%);
  }

  .card-content {
    position: relative;
  }

  .img-container {
    margin: -3rem 0;
    display: flex;
    justify-content: center;
  }

  form {
    display: grid;
    gap: 1rem;
    margin-top: .5rem;
  }

  input {
    height: 48px;
  }

  input,
  textarea {
    border: none;
    border-radius: 0.5rem;
    padding: 0 .5rem;
    width: 100%;
    box-sizing: border-box;
    font-size: 1rem;
  }

  textarea {
    padding: 1rem .5rem;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
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
