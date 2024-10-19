<script>
  import { onMount } from 'svelte';
  var ujadat = {}
  import Cica from './lib/Cica.svelte'
  var data = []
  onMount(async () => {
    data = await fetch('http://localhost:8000/posts')
    .then(r => r.json())
  })
</script>
<main>
  <Cica bind:adat={ujadat} bind:data/>
{#each data as d}
  <p>{d.title}
    <button class="x" on:click={async() => {
      let answ = await fetch(`http://localhost:8000/posts/${d.id}`,
       {method: 'DELETE'})
      if (answ.ok)
        data = data.filter(x => x.title !== d.title)
    }}>Töröl</button>
  </p>
{/each}
</main>
