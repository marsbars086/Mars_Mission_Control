<script>

const api_url ="https://zenquotes.io/api/quotes/";
import craftingquote from "../lib/images/craftingquote.webp"

async function getapi(url)
{
  const response = await fetch(url);
  var data = await response.json();
  console.log(data);
}

</script>

<div>
    <!-- <p>not working at all</p>
    <button onclick={()=> getapi(api_url)}>do u want to be inspired</button> -->
    <img src={craftingquote} alt="a quote about crafting" width="300px" height="300px"/>

</div>

<style>

</style>