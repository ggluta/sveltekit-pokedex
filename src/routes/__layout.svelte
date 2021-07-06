<script>
    import Navigation from '../components/navigation.svelte'
</script>

<!-- global infection of tailwind css -->
<style global lang="postcss">
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
</style>

<div class="p-8 max-w-6xl mx-auto">
    <Navigation/>
    <slot></slot>
</div>