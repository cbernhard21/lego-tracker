<script>
  export let lego;
</script>

<article class="card">
    <a href="/">
      <img src="images/{lego.image}" alt="{lego.name}">
    </a>
    <div class="card-text">
      <h2>{lego.name}</h2>
      <p>{lego.category}</p>
    </div>
    
</article>

<style>
  .card {
    border-radius: 1rem;
   box-shadow: 3px 3px 3px 1px rgba(0,0,0,.1);
  }

  .card-text {
    margin: .5rem;
  }

  img {
    height: 75%;
    object-fit: cover;
    border-top-left-radius: 1rem;
    border-top-right-radius: 1rem;
  }
</style>