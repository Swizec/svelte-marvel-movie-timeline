<script>
  import MarvelMovies from "./MarvelMovies.js";
  import Movie from "./Movie.svelte";
  import Header from "./Header.svelte";
  import Footer from "./Footer.svelte";

  let index = 0;

  function nextMovie() {
    index = (index + 1) % MarvelMovies.length;
  }

  function prevMovie() {
    index = index - 1;
    if (index < 0) {
      index = MarvelMovies.length - 1;
    }
  }
</script>

<style>
  .grid-container {
    display: grid;
    grid-template-columns: 0.1fr 2.9fr 0.1fr;
    grid-template-rows: 0.1fr 2.8fr 0.1fr;
    grid-template-areas: "h1 h2 h3" "b1 b2 b3" "f1 f2 f3";
  }

  button {
    cursor: pointer;
  }
</style>

<div class="grid-container">
  <Header />

  <button on:click={prevMovie} style="grid-area:b1">👈</button>

  <Movie {...MarvelMovies[index]} />

  <button on:click={nextMovie} style="grid-area:b3">👉</button>

  <Footer />
</div>
