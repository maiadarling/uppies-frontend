<script lang="ts">
  interface Site {
    name: string
    url: string
  }

  let sites: Site[] = [
    { name: 'Example Site 1', url: 'https://example1.com' },
    { name: 'Example Site 2', url: 'https://example2.com' },
    { name: 'Example Site 3', url: 'https://example3.com' }
  ]
</script>

<h1>Sites</h1>

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
