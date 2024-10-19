<script>
    export let adat
    export let data
</script>
<input type="text" bind:value={adat.title} placeholder="Cica">
<button class="x" on:click={async () => {
    let answ = await fetch('http://localhost:3000/posts', {
      method: 'POST',
      headers: {'Content-Type': 'application/json'},
      body: JSON.stringify(adat)
    })
    if (answ.ok) {
        adat.title = ""
        data = await fetch('http://localhost:3000/posts')
        .then(r => r.json())
    }
}}>Felvesz</button>