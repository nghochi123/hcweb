<!-- SKILLS -->
<script>
  import { quintInOut } from "svelte/easing";
  import Chip from "./Chip.svelte";

  function fromRight(node, { duration }) {
    return {
      duration,
      css: (t) => {
        const eased = quintInOut(t);
        return `
                    transform: translate3d(${(1 - eased) * 100}%,0,0);
                    `;
      },
    };
  }
</script>

<div transition:fromRight={{ duration: 800 }} class="panel">
  <a class="close" href="#home">
    <svg
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 24 24"
      fill="none"
      stroke="black"
      stroke-width="1.25"
      stroke-linecap="round"
      stroke-linejoin="round"
      class="feather feather-x"
      ><line x1="18" y1="6" x2="6" y2="18" /><line
        x1="6"
        y1="6"
        x2="18"
        y2="18"
      /></svg
    >
  </a>
  <h2>Skills</h2>
  <article>
    <div class="pushright">
      <h1>Skills</h1>
      <h3>Spoken Languages</h3>
      <Chip text="English" />
      <Chip text="Mandarin" />
      <h3>Programming Languages</h3>
      <Chip text="Javascript" />
      <Chip text="Python" />
      <Chip text="C/C++" />
      <Chip text="Stata" />
      <h3>Front-End</h3>
      <Chip text="React" />
      <Chip text="Vue" />
      <Chip text="Svelte" />
      <Chip text="React Native" />
      <Chip text="Flutter" />
      <!-- <Chip text="Material UI" />
      <Chip text="Vuetify" />
      <Chip text="Bootstrap" /> -->
      <h3>Back-End</h3>
      <Chip text="Express" />
      <Chip text="Django" />
      <Chip text="MongoDB" />
      <Chip text="SQL" />
      <!-- <Chip text="PostgreSQL" /> -->
      <h3>Machine Learning</h3>
      <Chip text="Tensorflow" />
      <Chip text="Pytorch" />
      <Chip text="OpenCV" />
      <h3>Blockchain</h3>
      <Chip text="Solidity" />
      <Chip text="SmartPy" />
      <Chip text="Web3.js" />
      <h3>Others</h3>
      <Chip text="Git" />
      <Chip text="Arduino" />
      <!-- <Chip text="Azure" /> -->
      <!-- <Chip text="Firebase" /> -->
      <Chip text="LaTeX" />
    </div>
  </article>
</div>

<style>
  .close {
    left: 0px;
  }
  .pushright {
    margin-left: 20px;
  }
  .panel {
    top: 3vh;
    right: 0px;
    height: 94vh;
    min-width: 330px;
    width: 94vw;
    border-radius: 15px 0px 0px 15px;
    z-index: 4;
  }
  h2 {
    padding-right: 10px;
    flex-direction: row-reverse;
  }

  @media only screen and (max-width: 1000px) {
    .panel {
      width: 500px;
    }
  }
  @media only screen and (max-width: 600px) {
    .panel {
      width: 85vw;
    }
  }
</style>
