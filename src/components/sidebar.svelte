<script lang="ts">
  import { page } from '$app/stores'
</script>

<aside class="sidebar flex column p-md">
  <nav class="nav flex column gap-xl gap-xl@md">
    <a href="/sites" class:active={$page.url.pathname === '/sites'}>Sites</a>
  </nav>
</aside>

<style lang="scss">
  .sidebar {
    --u-sidebar-background-color: var(--u-color-secondary);
    --u-sidebar-link-color: var(--u-link-color-on-secondary);

    background-color: var(--u-sidebar-background-color);
    min-width: 200px;
    font-size: 1.2rem;

    a {
      color: var(--u-sidebar-link-color);
      text-decoration: none;
    }
  }
</style>
