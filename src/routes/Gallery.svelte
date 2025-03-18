<script>
    import crochet_hat from "../lib/images/crochet_hat.jpg"
    import crochet_bunny from "../lib/images/crochet_bunny.avif" 
    import crochet_blanket from "../lib/images/crochet_blanket.jpg"

    let gallery_images = $state(
        [
        {image: crochet_hat, alt: "a crochet hat"},
        {image: crochet_bunny, alt: "a crochet bunny"},
        {image: crochet_blanket, alt: "a crochet blanket"}
    ])
</script>

<div>
    <h1> Gallery </h1>
    {#each gallery_images as { image, alt }}
    <img src={image} alt={alt} width="100px" height="100pxpx"/>
    {/each}
</div>

<style>
    h1 {
        justify-self: center;
        font-family: 'Londrina Outline', system-ui;
        font-size: 50px;
        font-weight: lighter;
    }
</style>