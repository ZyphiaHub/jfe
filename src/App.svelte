<script>
  var cicanev = 'Mici'
  import Cica from './lib/Cica.svelte'

</script>

<main>
  <Cica bind:name={cicanev}/>
  {cicanev}
</main>

