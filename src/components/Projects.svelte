<!-- Projects -->
<script>
    import { quintInOut } from "svelte/easing";
    import ProjectCard from "./ProjectCard.svelte";

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
    <h2>Projects</h2>
    <article>
        <div class="forprojectcard">
            <ProjectCard
                title="Algorithm Visualisation Tool"
                subtext="An algorithm visualisation tool that currently has 4 sorting algorithms, as well as a simple pathfinding algorithm."
                image="/visualisation.png"
                link="https://vis.nghochi.xyz/"
            />
            <ProjectCard
                title="BubbleTeaSort"
                subtext="A mobile application that helps you find the best bubble tea for your location and preference"
                image="/bubbleteasort.png"
                link="https://www.youtube.com/watch?v=uCoDD0N2cRA"
            />
            <ProjectCard
                title="CraiyoNFT"
                subtext="An NFT marketplace for users to mint and view 3D panoramic NFTs on the Tezos blockchain"
                image="/craiyonft.png"
                link="https://www.youtube.com/watch?v=en0Rm-tb4LE"
            />
            <ProjectCard
                title="Word-Tris"
                subtext="An online web game made with React, Express and Socket.io. Built for iNTUition 2022 with the team Basket Boys."
                image="/wordtris.png"
                link="https://www.youtube.com/watch?v=URQHyfBUpwg"
            />
            <!-- <ProjectCard
        title="Shortener"
        subtext="A URL shortener made with Vue (Nuxt) and Firebase."
        image="/shortener.png"
        link="https://s.nghochi.xyz/"
      />
      <ProjectCard
        title="Real Time Chat App"
        subtext="An app that utilises Web Sockets (using the socket.io npm module) to allow the real time exchange of information."
        image="/chatapp.png"
        link="https://chatapp.nghochi.xyz/"
      /> -->
            <!-- <ProjectCard
        title="SG-Info"
        subtext="An app that gets information from APIs online and presents them in a more human readable format."
        image="/weather.png"
        link="https://sg-info-hc.netlify.app/"
      /> -->
            <!-- <ProjectCard
        title="Generation"
        subtext="A mobile app built during Brainhack 2021 to help elderly get accustomed to post Covid life."
        image="/generation.png"
        link="https://www.youtube.com/watch?v=h_8WtiIeOTU"
      /> -->
        </div>
    </article>
</div>

<style>
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
            width: 97vw;
        }
    }
    @media only screen and (max-width: 905px) {
        .forprojectcard {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
    }
    @media only screen and (max-width: 750px) {
        .panel {
            width: 97vw;
        }
    }
</style>
