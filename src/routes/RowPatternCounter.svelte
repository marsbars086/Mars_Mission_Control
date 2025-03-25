<script>
    import Button from "./button.svelte"
    let DesiredNumPatternRows = $state()
    let ShowPatternTracker = $state(false)
    let NumPatternIterations = $state(0)
    let count = $state(0)
    function changecount(addorsubtract){
        if (addorsubtract === "add"){
            count += 1
        } else {
            count -= 1
        }
        CheckForPatternCompletion($state.snapshot(count))
    }

    function CheckForPatternCompletion(currentcount){
        if (currentcount === DesiredNumPatternRows){
            count = 0
            NumPatternIterations += 1
        }
    }

    function ResetCounter(){
        ShowPatternTracker = false
        count = 0
        NumPatternIterations = 0
        DesiredNumPatternRows = 0 
    }

</script>

<div class="PatternCounter">
    <button 
    onclick={()=> ResetCounter()}
    > 
    Reset 
    </button>
    <h1>Pattern Counter</h1>




    
    {#if ShowPatternTracker}
        <p>Row {count} of {DesiredNumPatternRows} completed | Pattern completed {NumPatternIterations} times</p>
        <Button class = "danger lg" on:click={() => changecount("subtract")}>
            -
        </Button>
        <Button class="primary lg" on:click={() => changecount("add")}>
            +
        </Button>
    {:else}
        <div>
            <div class="PatternInput">
                <p>Pattern repeats every </p>
                <input type="number"bind:value={DesiredNumPatternRows} placeholder="#" style="width: 40px; margin:0px">
                <p>rows</p>
                <button onclick={()=> ShowPatternTracker = true}>submit</button>
            </div>
        </div>
    {/if}
</div>

<style>
        h1{
        font-family: 'Londrina Outline', system-ui;
        font-size: 50px;
        font-weight: lighter;
    }
    .PatternCounter {
        justify-items: center;
    }
    .PatternInput {
        display: flex;
        flex-direction: row;
        align-items: center;
        width: 300px;
        justify-content: space-around;
    }
</style>