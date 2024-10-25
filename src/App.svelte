<script>
  import Cica from './lib/Cica.svelte';

  // @ts-ignore
  import Counter from './lib/Counter.svelte';
  // @ts-ignore
  import Masik from './lib/Masik.svelte';

  var selected = 'Counter'
</script>

<main>
  <div class="menu">
    <button on:click={() => (selected = 'Counter')}>Counter</button>
    <button on:click={() => (selected = 'mv')}>Másik valami</button>
    <button on:click={() => (selected = 'Cica')}>Cica</button>
  </div>
  <div>
    {#if selected === 'mv'}
      <Masik />
    {:else if selected === 'Counter'}
      <Counter />
    {:else if selected === 'Cica'}
      <Cica />
    {/if}
  </div>
</main>

<style>
  div.menu {
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100%;
    height: 20px;
    background-color: #333;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  div.menu button {
    font-size: 12px;
    padding: 2px 20px;
    margin: 2px;
  }
  main {
    background-color: aquamarine;
  }
</style>