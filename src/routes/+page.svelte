<script>
    import Button from "./button.svelte"
    import RowCounter from "./RowCounter.svelte";
    import ProjectTracker from "./ProjectTracker.svelte";
    import Gallery from "./Gallery.svelte";
    import Quotes from "./Quotes.svelte";
    import '@fontsource/londrina-outline';
    function hihi() {
        console.log("hello")
    }

</script>

<div class="hi_svelte">
    <div class="specialwebsitetitle">
    Crafting Dashboard!
    </div>
    <div style="height: 1px; background-color: #8BBF75"></div>

<div class="body">
    <div class="componentcolumn">
        <div 
        class="shadowedboxsmall"
        >
        <ProjectTracker/>
        </div>

        <div 
        class="shadowedboxsmall"
        >
        <Gallery/>
        </div>
    </div>

    <div 
    class="shadowedboxpinterest"
    >
    <script 
    type="text/javascript" 
    async defer src="//assets.pinterest.com/js/pinit.js">
    </script>
    <a data-pin-do="embedBoard" 
    data-pin-board-width="320" 
    data-pin-scale-height="580" 
    data-pin-scale-width="80" 

    href = "https://www.pinterest.com/mahumcrochets/crochet-ideas-for-when-youre-bored/"
    >
    <!-- href = "https://www.pinterest.com/mahumcrochets/crochet-room-decor/" -->
    <!-- I would consider having a random pinterest board generate! -->
    <!-- href="https://www.pinterest.com/artlaudinglisa/crochet-and-knit-board/" -->
    <!-- href="https://www.pinterest.com/anapinskywalker/style/" -->
    <!-- href = "https://www.pinterest.com/marsresser/crochet/"
    heres my crochet board... cant do it cus its private -->
    pinterest
    </a>
    </div>

    <div class="componentcolumn">
        <div 
        class="shadowedboxsmall"
        >
        <Quotes/>
        </div>

        <div
        class="shadowedboxsmall"
        >
        <RowCounter/>
        </div>
    </div>
    </div>

</div>


<style>
    .specialwebsitetitle {
        font-family: 'Londrina Outline', system-ui;
        font-size: 50px;
        /* font-weight: bold; */
        padding-top: 20px;
        padding-bottom: 20px;
        margin-left: 20px;
        /* border:2px solid #8BBF75; */
    }
    /* h1 {
        font-family: 'Londrina Outline', system-ui;
    } */
    .hi_svelte {
        /* background-color: #F8D49D; */
        /* background-color: #F9E29A; */
        background-color: #D5F0C0;

        /* background-color: #FFEE8C; */
        
    }
    .body{
        display:flex; 
        flex-direction:row;
        flex-wrap: wrap;
        justify-content: space-between;

    }
    .componentcolumn{
        display:flex; 
        flex-direction:column
    }
    .shadowedboxsmall{
        background-color: white;
        border-radius: 25px;
        /* border: 2px solid #73AD21; */
        padding: 20px;
        margin: 20px;
        width: 340px;
        height: 300px;
        justify-items: center;
        /* box-shadow: 10px 10px 5px rgb(128, 128, 128); */
        /* box-shadow: 10px 10px 5px #B5A88D; */
        box-shadow: 10px 10px 5px #8BBF75;
        /* box-shadow: 10px 10px 5px #A0D08B; */
        
        
        align-content: center;
    }
    .shadowedboxpinterest{
        background-color: white;
        border-radius: 25px;
        /* border: 2px solid #73AD21; */
        padding: 20px;
        margin: 20px;
        width: 340px;
        height: 680px;
        justify-items: center;
        box-shadow: 10px 10px 5px #8BBF75;
    }
</style>
