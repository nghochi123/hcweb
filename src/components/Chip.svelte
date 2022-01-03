<script>
  export let text = "";
</script>

<div class="chip">
  <div class="chip-content">{text}</div>
</div>

<style>
  .chip {
    display: inline-flex;
    flex-direction: row;
    background-color: white;
    border: none;
    cursor: default;
    height: 36px;
    outline: none;
    padding: 0;
    font-size: 14px;
    white-space: nowrap;
    align-items: center;
    border-radius: 5px;
    vertical-align: middle;
    text-decoration: none;
    justify-content: center;
    margin-bottom: 10px;
  }
  .chip-content {
    font-family: Montserrat;
    cursor: inherit;
    display: flex;
    align-items: center;
    user-select: none;
    white-space: nowrap;
    padding-left: 12px;
    padding-right: 12px;
  }
</style>
