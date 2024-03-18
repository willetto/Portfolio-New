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
    position: relative;

    display: flex;
    flex-direction: column;
    gap: 3rem;
    align-items: center;
    justify-content: center;

    height: 100vh;
    padding: 0 20px;

    text-align: center;

    background-color: var(--c-white);
    &::before {
      pointer-events: none;
      content: "";

      position: absolute;
      z-index: 0;
      bottom: 0;
      left: 0;

      width: 100%;
      height: 200px;

      opacity: 0.8;
      background-image: var(--texture-url);
      background-repeat: no-repeat;
      background-position: bottom;
      background-size: cover;
      mix-blend-mode: darken;
    }
  }
  .hero-title { 
    position: relative;
    background-image: linear-gradient(120deg, var(--c-orange) 0%, var(--c-yellow) 100%);
    background-clip: text;

    -webkit-text-fill-color: transparent;
    &::before {
      pointer-events: none;
      content: attr(title);

      position: absolute;
      inset: 0;

      text-shadow: -3px 2px 6px #fff, 0 0 0 var(--c-black);
      
      opacity: 0.4;
      background-color: #000;
      background-clip: text;
      mix-blend-mode: multiply;

    }
  }
  .h1 {
    color: var(--c-green);
  }
  .subtitles{
    z-index: 1;}
  .highlight {
    position: relative;
    
    &::before {
      pointer-events: none;
      content: "";

      position: absolute;
      top: 37%;
      right: .5rem;

      width: 99%;
      height: 60%;

      background-color: var(--c-yellow-o9);
      mix-blend-mode: multiply;

    }
  }

  
</style>