<script>
    let PatternRows = $state('')
    let ShowPatternTracker = $state(false)
</script>

<div class="PatternCounter">
    <p>Pattern repeats every X rows:</p>
    <input bind:value={PatternRows} placeholder="#stiches/rows">
    <button onclick={()=> ShowPatternTracker = true}>submit</button>
    {#if ShowPatternTracker}
        <p>Pattern trackerrr</p>
    {:else}
        <div></div>
    {/if}
</div>

<style>
    .PatternCounter {
        justify-items: center;
    }
</style>