<!-- About -->
<script>
  import { quintInOut } from "svelte/easing";

  function fromLeft(node, { duration }) {
    return {
      duration,
      css: (t) => {
        const eased = quintInOut(t);
        return `
                    transform: translate3d(-${(1 - eased) * 100}%,0,0);
                    `;
      },
    };
  }
</script>

<div transition:fromLeft={{ duration: 800 }} class="panel">
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
  <h2>About</h2>
  <article />
</div>

<style>
  .close {
    right: 0px;
  }
  .panel {
    top: 3vh;
    height: 94vh;
    min-width: 300px;
    right: 3vw;
    width: 97vw;
    border-radius: 0px 15px 15px 0px;
  }
  h2 {
    padding-left: calc(1vw + 10px);
    flex-direction: row;
  }

  a {
    text-decoration: underline;
  }
  @media only screen and (max-width: 1000px) {
    .panel {
      width: 75vw;
    }
  }
  @media only screen and (max-width: 750px) {
    .panel {
      width: 85vw;
    }
  }
</style>
