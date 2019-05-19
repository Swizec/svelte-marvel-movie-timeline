<script>
  export let title;
  export let description;
  export let image;
  export let yearOut;
</script>

<h2>{title}</h2>

<img src={image} alt={`${title} movie thumbnail`} />

<p>{description}</p>
