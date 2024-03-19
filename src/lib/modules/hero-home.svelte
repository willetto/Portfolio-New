<script>
  import texture from '$lib/imgs/textures/cardboard.jpg';
</script>

<div class="hero-wrapper" style={`--texture-url: url(${texture})`}>
  <h1 class="h0 hero-title" title="Hi, I'm Trey">Hi, I'm Trey</h1>
  <div class="subtitles">
    <p class="h1">I care about <span class="highlight">crafting thoughtfully.</span></p>
    <p class="h1">I work as a <span class="highlight">front-end web developer.</span></p>
    <p class="h1">I aim to <span class="highlight">empower others.</span></p>
  </div>
</div>
<style>
  .hero-wrapper {
    --local-bg-color: var(--c-white);
    --local-font-color: var(--c-green);
    --local-highlight-gradient: conic-gradient(from 190deg at 0% 0% in oklch, var(--c-yellow) 60%, var(--c-yellow-o8) 75%, var(--c-yellow) 95%);
    --local-highlight-blend: multiply;
    --local-texture-opacity: 0.2;

    position: relative;

overflow: hidden;
    display: flex;
    flex-direction: column;
    gap: 3rem;
    align-items: center;
    justify-content: center;

    height: 100vh;
    padding: 0 20px;

    text-align: center;

    background-color: var(--local-bg-color);

    transition: background-color 0.3s ease-in-out;
    &::before {
      pointer-events: none;
      content: "";

      position: absolute;
      z-index: 0;
      bottom: -100px;
      left: 0;

      width: 100%;
      height: 400px;

      opacity: var(--local-texture-opacity);
      background-image: var(--texture-url);
      background-repeat: no-repeat;
      background-position: bottom;
      background-size: cover;
      mix-blend-mode: multiply;
    }
  }
  .hero-title { 
    position: relative;
    background-image: var(--gradient-orange);
    background-clip: text;

    -webkit-text-fill-color: transparent;
    &::before {
      pointer-events: none;
      content: attr(title);

      position: absolute;
      inset: 0;

      text-shadow: -3px 2px 6px #fff, 0 0 0 var(--c-black);
      
      opacity: 0.4;
      background-color: var(--c-black);
      background-clip: text;
      mix-blend-mode: multiply;

    }
  }
  .h1 {
    color: var(--local-font-color);
    transition: color 0.3s ease-in-out;

  }
  .subtitles{
    /* z-index: 1; */
  }
  .highlight {
    position: relative;
    color: var(--local-font-color);
    transition: color 0.3s ease-in-out;

    &::after{
      pointer-events: none;
      content: "";

      position: absolute;
      z-index: 2;
      top: 37%;
      right: .5rem;

      width: 99%;
      height: 60%;

      opacity: .5;
      background-image: var(--noise-1);
      mix-blend-mode: overlay;

    }

    &::before {
      pointer-events: none;
      content: "";

      position: absolute;
      top: 37%;
      right: .5rem;

      width: 99%;
      height: 60%;

      background-image: var(--local-highlight-gradient);
      background-size: cover;
      background-blend-mode: screen;
      mix-blend-mode: var(--local-highlight-blend);
    }
  }

  @media (prefers-color-scheme: dark) {
    .hero-wrapper {
      --local-bg-color: var(--c-blue-dark);
      --local-font-color: var(--c-white-o9);
      --local-highlight-gradient: conic-gradient(from 190deg at 0% 0% in oklch, var(--c-blue-o8) 60%, var(--c-blue) 75%, var(--c-blue-o8) 95%);
      --local-highlight-blend: screen;
      --local-texture-opacity:0.4;
      /* mix-blend-mode: ; */

    }
  }
  
</style>