<script>
  var cicanev = 'Mici'
  import Cica from './lib/Cica.svelte'
  var data = []
</script>

<main>
  <Cica bind:name={cicanev}/>
  {cicanev}
  <hr>
  <button on:click={async () => {
    data = await fetch('http://localhost:8000/posts')
    .then(r => r.json())
  }}>Cica</button>
{#each data as d}
  <p>{d.title}
    <button class="x">Töröl</button>
  </p>
{/each}
</main>
<style>
  button.x {
    padding: 5px;
    font-size: 12px;
  }
</style>
