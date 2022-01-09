<!-- About -->
<script>
  import { quintInOut } from "svelte/easing";
  import TextCard from "./TextCard.svelte";

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
  <article>
    <div>
      <div class="imagediv">
        <img src="/montreal.jpg" alt="hc" class="img" />
      </div>
      <p>
        Hello! My name is Ng Ho Chi, and I'm a Computer Science Major at NTU,
        studying under the CN Yang Scholarship.
      </p>
      <p>
        I enjoy all things tech, and try to dabble myself in many different
        areas such as Web Development, Machine Learning, Cybersecurity and
        Blockchain.
      </p>
      <p>
        In my free time, I participate in hackathons and CTFs to improve my
        technical skills while having fun.
      </p>
    </div>
    <div class="pushright">
      <h1>Achievements</h1>
      <h3>International</h3>
      <div class="fortextcard">
        <TextCard
          title="Participant"
          subtitle="RoboCup International 2018 - Montreal, Canada"
        />
      </div>
      <h3>National</h3>
      <div class="fortextcard">
        <TextCard
          title="Champions"
          subtitle="RoboCup Singapore 2018 - Rescue Line"
        />
        <TextCard
          title="4th place"
          subtitle="HTX Investigator's Challenge 2021"
        />
        <TextCard
          title="Medal Winner (Top Score)"
          subtitle="UNSW Global ICAS Assessment - Science"
        />
      </div>
    </div>
  </article>
</div>

<style>
  .pushright {
    margin-left: 20px;
  }
  .img {
    width: 500px;
  }
  .imagediv {
    display: flex;
    justify-content: center;
    margin-bottom: 30px;
  }
  .close {
    right: 0px;
  }
  .panel {
    top: 3vh;
    height: 94vh;
    min-width: 300px;
    left: 0;
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
  @media only screen and (max-width: 880px) {
    .img {
      width: 400px;
    }
    .fortextcard {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
  }
  @media only screen and (max-width: 750px) {
    .panel {
      width: 85vw;
    }
    .img {
      width: 250px;
    }
  }
</style>
