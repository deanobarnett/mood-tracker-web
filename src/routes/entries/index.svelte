<script context="module">
  export async function preload({ params }) {
    const response = await this.fetch("http://localhost:8080/entries?per_page=10", {
      headers: {
        'Access-Control-Allow-Origin':'*'
      }
    });
    const entries = await response.json();
    return { entries };
  }
</script>

<script>
  import LoadingIcon from '../../components/LoadingIcon.svelte';
  export let entries;
</script>

<svelte:head>
  <title>Entries</title>
</svelte:head>

<h1>Recent entries</h1>

{#await entries}
  <LoadingIcon />
{:then entries}
  {#each entries as entry}
    {#if entry.date !== ""}
      <p>
      <a class="btn btn-link" rel=prefetch href='entries/{entry.id}'>{new Date(entry.date).toDateString()}</a>
      </p>
    {/if}
  {/each}
{:catch error}
    <p style="color: red">{error.message}</p>
{/await}
