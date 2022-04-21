<script>
  import Header from '$lib/components/Header.svelte';
  import '$lib/css/global.css';
</script>

<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@300;400;600&display=swap" rel="stylesheet" />
  <title>Colin's Lego Tracker</title>
</svelte:head>

<header>
  <Header />
</header>

<main>
  <slot></slot>
</main>


<style>
    header {
    width: 100%;
    background-color: var(--main-bg-color)
  }

  main {
    width: 100%;
  }
</style>