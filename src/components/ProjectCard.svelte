<script>
  export let title = "";
  export let subtext = "";
  export let image = "";
  export let link = "";
</script>

<div class="container">
  <div class="row">
    <div class="image">
      <a href={link}>
        <img id="cimg" src={image} alt="project" />
        <div class="details">
          <h1>{title}</h1>
          <p class="subtext">{subtext}</p>
        </div>
      </a>
    </div>
  </div>
</div>

<style>
  .container {
    margin: 20px;
    display: inline-flex;
    flex-direction: row;
  }
  .row {
    width: 100%;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }
  #cimg {
    height: 300px;
  }
  .image {
    background: #000;
    position: relative;
    flex: 1;
    width: 380px;
    height: 220px;
    overflow: hidden;
    border-radius: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .image img {
    opacity: 0.3;
    position: relative;
    vertical-align: top;
    transition: all 0.5s ease;
  }
  .image:hover img {
    opacity: 0.5;
    transform: scale(1.1);
  }
  .details {
    z-index: 1;
    position: absolute;
    top: 0;
    right: 0;
    color: #fff;
    width: 100%;
    height: 100%;
    text-align: center;
  }
  .details h1 {
    font-size: 20px;
    font-weight: 600;
    margin-top: 20px;
    justify-content: center;
  }

  .subtext {
    font-family: "Montserrat";
    opacity: 0;
    transition: all 0.2s ease-in-out;
    font-size: 90%;
  }
  .image:hover .subtext {
    opacity: 1;
  }
  @media only screen and (max-width: 600px) {
    .image {
      width: 300px;
      height: 180px;
    }
    .subtext {
      opacity: 1;
    }
  }
</style>
