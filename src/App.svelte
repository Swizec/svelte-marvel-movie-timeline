<script>
  import MarvelMovies from "./MarvelMovies.js";
  import Movie from "./Movie.svelte";

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
  h1 {
    color: purple;
  }
</style>

<h1>Marvel Movie Timeline</h1>

<button on:click={prevMovie}>👈</button>

<Movie {...MarvelMovies[index]} />

<button on:click={nextMovie}>👉</button>

<p>
  Details borrowed from
  <a
    href="https://www.amctheatres.com/amc-scene/the-best-way-to-rewatch-the-mcu">
    AMC Theaters
  </a>
</p>
