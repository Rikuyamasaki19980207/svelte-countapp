<script lang="ts">
  import CardLength from './CardLength.svelte';
  import Counter from './Counter.svelte';
  import Card from './Card.svelte';
</script>

<div id="app">
  <div class="text-center" id="app">
    <h1 class="text-6xl">Multiple Counter</h1>
    <Card />
    <Counter />
    <CardLength />
  </div>
</div>

<style>
  .text-6xl {
    font-size: 4rem;
  }

  h1 {
    font-size: inherit;
    font-weight: inherit;
    margin: 0;
  }

  .text-center {
    text-align: center;
  }
</style>
