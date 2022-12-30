<script>
  import Canvas from './Canvas.svelte'
  import Counter from './Counter.svelte'
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte Visualizations" />
</svelte:head>

<section>
  <Canvas />
  <Counter />
</section>

<style>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex: 0.6;
  }
</style>
