<script>
    export let adat
    export let data
</script>
<input type="text" bind:value={adat.title} placeholder="Cica">
<button class="x" on:click={async () => {
    let nd = {id: Math.random().toString(), title: adat.title}
    await fetch('http://localhost:8000/posts', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify(nd)
    })
    data.push(nd)
    data = data
    adat.title = ""
}}>Felvesz</button>