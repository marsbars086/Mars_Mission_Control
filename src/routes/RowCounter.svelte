<script>
        import Button from "./button.svelte"
        import '@fontsource/londrina-outline';
    
    function changecount(addorsubtract){
        if (addorsubtract === "add"){
            count += 1
        } else {
            count -= 1
        }
        CheckForDesired($state.snapshot(count))
    }
    
    //pretty sure this function logic is pretty jacked
    //BUT WE LIVE AND WE LEARN
    function CheckForDesired(currentcount){
        console.log(desiredcount)
        if (desiredcount === "") {
            alert("no desired count yet!")
        } else {
            let currentdesirecount = Number(desiredcount)
            CheckForCompletion(currentdesirecount, currentcount)
        }

    }

    function CheckForCompletion(currentdesirecount, currentcount){
                if(currentcount === currentdesirecount){
                    alert("STOP CROCHETING")
                } else if (currentcount < currentdesirecount){
                    console.log('keep going bud')
                } else {
                    let howMuchOver = currentcount - currentdesirecount
                    // console.log(howMuchOver)
                    alert('STOP! You are ' + howMuchOver + ' stiches over')
                }
            }

    function ResetCounter(){
        count = 0
        desiredcount = ""
    }
    let count = $state(0)
    let desiredcount = $state("")
</script>

<div class="rowcounter">
    <button 
    onclick={()=> ResetCounter()}
    > 
    Reset 
    </button>
    <h1>Row Counter</h1>
    <div class = "countsbar">
    <p>count = {count}</p>
    <p>desired count =</p>
    <input bind:value={desiredcount} placeholder="#stiches/rows"/>
    </div>

    <Button class = "danger lg" on:click={() => changecount("subtract")}>
        -
    </Button>
    <Button class="primary lg" on:click={() => changecount("add")}>
        +
    </Button>

</div>

<style>
    h1{
        font-family: 'Londrina Outline', system-ui;
        font-size: 50px;
        font-weight: lighter;
    }
    input{
        width: 100px;
        height: 20px;
    }
        .rowcounter {
        justify-items: center;
    }

    .countsbar {
        display: flex;
        flex-direction: row;
        align-items: center;
        width: 300px;
        justify-content: space-around;
    }
</style>