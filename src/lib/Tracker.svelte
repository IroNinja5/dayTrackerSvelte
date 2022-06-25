<script lang="ts">
  export let name: string
  let complete: boolean = false

  $: if (complete) {
      console.log(`${name} is done!`);
  }

  function switchState() {
      complete = !complete;
  }
</script>

<button class:complete={complete} on:click={switchState}>{name}</button>

<style>
  button {
    font-family: inherit;
    font-size: inherit;
    padding: 1em 2em;
    color: #ff3e00;
    background-color: rgba(255, 31, 74, 0.1);
    border-radius: 2em;
    border: 2px solid rgba(255, 31, 74, 0);
    outline: none;
    width: 200px;
    font-variant-numeric: tabular-nums;
    cursor: pointer;
  }

  button:focus {
    border: 2px solid #ff3e00;
  }

  button:active {
    background-color: rgba(255, 31, 74, 0.2);
  }
  .complete {
    color: #33cc00;
    background-color: rgba(102, 255, 0, 0.2);
    border: 2px solid rgba(102, 255, 0, 0);
  }

  .complete:focus {
    border: 2px solid #66ff00;
  }

  .complete:active {
    background-color: rgba(102, 255, 0, 0.3);
  }
</style>
