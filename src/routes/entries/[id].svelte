<script context="module">
  export async function preload({ params }) {
    const res = await this.fetch(`http://localhost:8080/entries/${params.id}`);
    const entry = await res.json();
    return { entry };
  }
</script>

<script>
  import LoadingIcon from '../../components/LoadingIcon.svelte';

  export let entry;

  const toDate = (date) => (new Date(date).toDateString());
</script>

<style>
</style>

<svelte:head>
  <title>{entry.date} | Entry</title>
</svelte:head>

{#await entry}
  <LoadingIcon />
{:then entry}
  <h1>{toDate(entry.date)}</h1>

  <div class='content'>
    <p> 😴 - {entry.sleep} </p>
    <p> 🙂 - {entry.mood} </p>
    <p> 😰 - {entry.stress} </p>
    <p> 📝 - {@html entry.notes || "N/A"} </p>
  </div>
{:catch error}
  <p style="color: red">{error.message}</p>
{/await}
