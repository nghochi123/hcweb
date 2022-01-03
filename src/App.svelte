<script>
  // Dependency imports
  import { onMount } from "svelte";
  import { fly, fade } from "svelte/transition";

  // Own imports
  import TopRight from "./components/TopRight.svelte";
  import BottomLeft from "./components/BottomLeft.svelte";
  import TopLeft from "./components/TopLeft.svelte";
  import BottomRight from "./components/BottomRight.svelte";

  let p = false;
  let path = window.location.hash.substr(1) || "";
  function loader() {
    path = window.location.hash.substr(1);
  }
  onMount(() => {
    setTimeout(() => (p = true), 3500);
  });
</script>

<svelte:window on:hashchange={loader} />
<svelte:head>
  <meta name="robots" content="noindex nofollow" />
  <meta
    name="viewport"
    content="width=device-width, initial-scale=1.0, maximum-scale=1, user-scalable=0"
  />
  <html lang="en" />
</svelte:head>

<main>
  <div class="hero">
    <h1 id="hello">Hello, I'm</h1>
    <svg
      id="name"
      width="500"
      height="120"
      viewBox="-10 -10 500 120"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M79.416 3.632V104H66.312V58.496H15.192V104H2.08801V3.632H15.192V47.696H66.312V3.632H79.416Z"
        stroke="white"
        stroke-width="3"
        stroke-linecap="square"
      />
      <path
        d="M147.295 105.008C137.983 105.008 129.487 102.848 121.807 98.528C114.127 94.112 108.031 88.016 103.519 80.24C99.1031 72.368 96.8951 63.536 96.8951 53.744C96.8951 43.952 99.1031 35.168 103.519 27.392C108.031 19.52 114.127 13.424 121.807 9.104C129.487 4.688 137.983 2.48 147.295 2.48C156.703 2.48 165.247 4.688 172.927 9.104C180.607 13.424 186.655 19.472 191.071 27.248C195.487 35.024 197.695 43.856 197.695 53.744C197.695 63.632 195.487 72.464 191.071 80.24C186.655 88.016 180.607 94.112 172.927 98.528C165.247 102.848 156.703 105.008 147.295 105.008ZM147.295 93.632C154.303 93.632 160.591 92 166.159 88.736C171.823 85.472 176.239 80.816 179.407 74.768C182.671 68.72 184.303 61.712 184.303 53.744C184.303 45.68 182.671 38.672 179.407 32.72C176.239 26.672 171.871 22.016 166.303 18.752C160.735 15.488 154.399 13.856 147.295 13.856C140.191 13.856 133.855 15.488 128.287 18.752C122.719 22.016 118.303 26.672 115.039 32.72C111.871 38.672 110.287 45.68 110.287 53.744C110.287 61.712 111.871 68.72 115.039 74.768C118.303 80.816 122.719 85.472 128.287 88.736C133.951 92 140.287 93.632 147.295 93.632Z"
        stroke="white"
        stroke-width="3"
        stroke-linecap="square"
      />
      <path
        d="M248.489 53.744C248.489 43.952 250.697 35.168 255.113 27.392C259.529 19.52 265.529 13.376 273.113 8.96C280.793 4.544 289.289 2.336 298.601 2.336C309.545 2.336 319.097 4.976 327.257 10.256C335.417 15.536 341.369 23.024 345.113 32.72H329.417C326.633 26.672 322.601 22.016 317.321 18.752C312.137 15.488 305.897 13.856 298.601 13.856C291.593 13.856 285.305 15.488 279.737 18.752C274.169 22.016 269.801 26.672 266.633 32.72C263.465 38.672 261.881 45.68 261.881 53.744C261.881 61.712 263.465 68.72 266.633 74.768C269.801 80.72 274.169 85.328 279.737 88.592C285.305 91.856 291.593 93.488 298.601 93.488C305.897 93.488 312.137 91.904 317.321 88.736C322.601 85.472 326.633 80.816 329.417 74.768H345.113C341.369 84.368 335.417 91.808 327.257 97.088C319.097 102.272 309.545 104.864 298.601 104.864C289.289 104.864 280.793 102.704 273.113 98.384C265.529 93.968 259.529 87.872 255.113 80.096C250.697 72.32 248.489 63.536 248.489 53.744Z"
        stroke="white"
        stroke-width="3"
        stroke-linecap="square"
      />
      <path
        d="M441.947 3.632V104H428.843V58.496H377.723V104H364.619V3.632H377.723V47.696H428.843V3.632H441.947Z"
        stroke="white"
        stroke-width="3"
        stroke-linecap="square"
      />
      <path
        d="M477.426 3.632V104H464.322V3.632H477.426Z"
        stroke="white"
        stroke-width="3"
        stroke-linecap="square"
      />
    </svg>
  </div>
  {#if p}
    <a href="#about" in:fly={{ duration: 700, x: -45 }}> About </a>
    <a href="#projects" in:fly={{ duration: 700, y: 45 }}> Projects </a>
    <a href="#contact" in:fly={{ duration: 700, x: 45 }}> Contact </a>
    <a href="#skills" in:fly={{ duration: 700, x: 45 }}> Skills </a>
  {/if}
</main>

{#if path == "about" || path == "projects" || path == "contact" || path == "skills"}
  <div transition:fade={{ duration: 400 }} class="modal" />
{/if}
{#if path == "about"}
  <TopLeft />
{:else if path == "projects"}
  <BottomLeft />
{:else if path == "contact"}
  <BottomRight />
{:else if path == "skills"}
  <TopRight />
{/if}

<style>
  /* Global stuff */
  :global(body) {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
  :global(.panel) {
    height: 100%;
    background-color: rgba(0, 6, 37, 0.9);
    -webkit-backdrop-filter: brightness(8) blur(10px);
    backdrop-filter: brightness(8) blur(10px);
    overflow: hidden;
    position: fixed;
    z-index: 4;
  }
  :global(.close) {
    position: absolute;
    top: 0px;
    height: 65px;
    width: 65px;
    color: #2f2f2f;
    padding: 10px;
    background-color: white;
  }
  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
  :root {
    --bg-color: rgb(32, 35, 48);
  }
  /* Full screen */
  main {
    width: 100%;
    height: 100%;
    background-color: var(--bg-color);
  }
  /* Hero box (name + animation) */
  #hello {
    color: white;
    font-family: "Source Code Pro", monospace;
    position: relative;
    width: max-content;
    padding: 1px;
  }
  #hello::before,
  #hello::after {
    content: "";
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
  }

  #hello::before {
    background: var(--bg-color);
    animation: typewriter 2s steps(10) forwards;
  }

  #hello::after {
    width: 0.05em;
    background: white;
    animation: typewriter 2s steps(10) forwards, remove 0s ease-in 3s forwards,
      blink 750ms steps(2) infinite;
  }

  @keyframes blink {
    to {
      background: transparent;
    }
  }

  @keyframes remove {
    to {
      width: 0;
      height: 0;
      overflow: hidden;
    }
  }

  @keyframes typewriter {
    to {
      left: 100%;
    }
  }

  .hero {
    position: absolute;
    transform: translate3d(-50%, -50%, 0);
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  .modal {
    background-color: rgba(0, 0, 0, 0.35);
    position: fixed;
    z-index: 2;
    width: 100vw;
    height: 100vh;
    top: 0px;
    opacity: 1;
    left: 0px;
  }

  #name {
    animation: fill 0.5s ease forwards 3.6s;
  }

  #name path:nth-child(1) {
    stroke-dasharray: 535;
    stroke-dashoffset: 535;
    animation: line-anim 3s ease forwards;
  }
  #name path:nth-child(2) {
    stroke-dasharray: 566;
    stroke-dashoffset: 566;
    animation: line-anim 3s ease forwards 0.3s;
  }
  #name path:nth-child(3) {
    stroke-dasharray: 509;
    stroke-dashoffset: 509;
    animation: line-anim 3s ease forwards 0.6s;
  }
  #name path:nth-child(4) {
    stroke-dasharray: 535;
    stroke-dashoffset: 535;
    animation: line-anim 3s ease forwards 0.9s;
  }
  #name path:nth-child(5) {
    stroke-dasharray: 227;
    stroke-dashoffset: 227;
    animation: line-anim 3s ease forwards 1.2s;
  }

  @keyframes line-anim {
    to {
      stroke-dashoffset: 0;
    }
  }

  @keyframes fill {
    from {
      fill: transparent;
    }
    to {
      fill: white;
    }
  }

  /* Links */
  a {
    font-size: 2em;
    padding: 5px;

    padding-left: calc(20px + 0.5em);
    padding-right: 20px;
    color: white;
    font-family: "Montserrat", sans-serif;
    position: fixed;
    overflow: hidden;
    transition-duration: 0.4s;
    z-index: 1;
    letter-spacing: 0.5em;
    text-align: center;
    font-weight: 500;
    text-transform: uppercase;
    /* opacity: .7;
		transform-origin: left; */
  }
  a:nth-of-type(1) {
    top: 20px;
    left: 20px;
  }
  a:nth-of-type(2) {
    bottom: 20px;
    left: 20px;
  }
  a:nth-of-type(3) {
    bottom: 20px;
    right: 20px;
  }
  a:nth-of-type(4) {
    top: 20px;
    right: 20px;
  }
  a:hover {
    text-decoration: none;
    color: black;
    /* opacity: 1;
		transform: scale(1.1) */
  }
  a::before {
    content: "";
    top: 0px;
    left: 0px;
    position: absolute;
    z-index: -1;
    height: 100%;
    width: 100%;
    background-color: white;
    transition-duration: 0.4s;
  }
  a:nth-of-type(1)::before {
    transform: translate3d(-110%, 0px, 0);
  }
  a:nth-of-type(2)::before {
    transform: translate3d(0px, 110%, 0);
  }
  a:nth-of-type(3)::before {
    transform: translate3d(110%, 0px, 0);
  }
  a:nth-of-type(4)::before {
    transform: translate3d(0px, -110%, 0);
  }
  a:nth-of-type(n):hover::before {
    transform: translate3d(0px, 0px, 0);
  }

  /* Media Queries */
  @media only screen and (max-width: 850px) {
    #name,
    h1 {
      width: 400px;
    }
    h1 {
      font-size: 2.1em;
      top: calc(50% + 90px);
    }
    a {
      font-size: 1.8em;
    }
  }
  @media only screen and (max-width: 550px) {
    a {
      letter-spacing: 5px;
      padding: 0px;
      font-size: 1em;
      padding-left: 15px;
      padding-right: 10px;
    }
    #name,
    h1 {
      width: 300px;
    }
    h1 {
      font-size: 1.9em;
      top: calc(50% + 80px);
    }
  }
</style>
