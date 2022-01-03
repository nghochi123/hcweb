<script>
  export let title = "";
  export let subtitle = "";
</script>

<div class="container">
  <div class="card">
    <div class="title">{title}</div>
    <div class="subtitle">{subtitle}</div>
  </div>
</div>

<style>
  .container {
    font-family: Montserrat;
    display: inline-flex;
    flex-direction: row;
    margin-bottom: 10px;
    margin-right: 10px;
  }
  .card {
    min-width: 300px;
    max-width: 400px;
    background-color: white;
    padding: 8px;
    border-radius: 12px;
    display: flex;
    align-items: center;
    flex-direction: column;
    padding: 20px;
  }
  .title {
    font-weight: 600;
    font-size: 1.2em;
  }
  .subtitle {
    font-weight: 300;
    text-align: center;
  }
</style>
