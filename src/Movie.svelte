<script>
  export let title;
  export let description;
  export let image;
  export let yearOut;
</script>

<style>
  .main {
    grid-area: b2;

    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 0.1fr 400px 1.1fr;
    grid-template-areas: "title" "thumbnail" "description";
  }

  h2 {
    text-align: center;
    grid-area: title;
  }

  img {
    max-height: 100%;
    max-width: 640px;
    display: block;
  }

  .thumbnail {
    grid-area: thumbnail;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  p {
    grid-area: description;
    padding: 0 1em;
  }
</style>

<div class="main">
  <h2>{title}</h2>

  <div class="thumbnail">
    <img src={image} alt={`${title} movie thumbnail`} />
  </div>

  <p>{description}</p>

</div>
