<h1>Sample game board</h1>
<div id="gameboard-div">
  {#each Array(8).fill(0) as _}
    <div class="grid-cell-div"/>
  {/each}
</div>

<style>
  #gameboard-div {
    align-self: center;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-around;
    align-content: space-around;
    background-color: aliceblue;
    min-height: max-content;
    min-width: max-content;
    height: 100%;
    width: 100%;
  }

  .grid-cell-div {
    background-color: darkcyan;
    min-height: 100px;
    min-width: 100px;
    margin: 2%;
  }

  .grid-cell-div:hover {
    border-color: red;
    border-style: solid;
  }
</style>
