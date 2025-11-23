<script lang="ts">
  import { onMount } from 'svelte'

  interface Site {
    name: string
    url: string
  }

  let sites: Site[] = []
  let loading = true
  let error: string | null = null

  const getSites = async (): Promise<Site[]> => {
    await new Promise(resolve => setTimeout(resolve, 1))

    // Placeholder for fetching sites from an API or database
    return [
      { name: 'Example Site 1', url: 'https://example1.com' },
      { name: 'Example Site 2', url: 'https://example2.com' },
      { name: 'Example Site 3', url: 'https://example3.com' }
    ]
  }

  onMount(async () => {
    try {
      sites = await getSites()
    } catch (err) {
      error = err instanceof Error ? err.message : 'Failed to load sites'
    } finally {
      loading = false
    }
  })
</script>

<h1>Sites</h1>

{#if loading}
  <p>Loading sites...</p>
{:else if error}
  <p class="error">Error: {error}</p>
{:else}
  <table>
    <caption>List of available sites</caption>
    <thead>
      <tr>
        <th scope="col">Site Name</th>
        <th scope="col">URL</th>
        <th scope="col">Actions</th>
      </tr>
    </thead>
    <tbody>
      {#each sites as site}
        <tr>
          <td>{site.name}</td>
          <td>
            <a href={site.url} target="_blank" rel="noopener noreferrer">
              {site.url}
            </a>
          </td>
          <td>
            <button type="button" aria-label="Visit {site.name}">
              Visit Site
            </button>
          </td>
        </tr>
      {/each}
    </tbody>
  </table>
{/if}
