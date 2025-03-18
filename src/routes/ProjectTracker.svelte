<script>
    import ProjectEntries from "./ProjectEntries.svelte";
    import Button from "./button.svelte";
    import Modal from "./Modal.svelte";

    let projects = $state([
        {name: "Sweater", hook: "5.5 mm", pattern: "https.blah"},
        {name: "Scarf", hook: "4 mm", pattern:"https.wow"}
    ])
    let newProject = $state(
        {name: "", hook: "", pattern: ""}
    );

    function createProject(){
        projects.push($state.snapshot(newProject))
        newProject.name = ""
        newProject.hook = ""
        newProject.pattern = "" 
    }

    let showModal = $state(false);
</script>

<div class="shadowedbox">
<h1>Project Tracker</h1>

    <ProjectEntries projects = {projects}/>
</div>

<Button class="primary lg" on:click={() => (showModal = true)}>
    +
</Button>


<Modal bind:showModal>
	{#snippet header()}
		<h2>
            Project Creator
		</h2>
	{/snippet}

    <p>Hi! Lets make a new project</p>
    <input bind:value={newProject.name} placeholder="project name"/>
    <input bind:value={newProject.hook} placeholder="hook size"/>
    <input bind:value={newProject.pattern} placeholder="project pattern"/>
    <button onclick={()=> createProject()}>submit</button>

</Modal>

<style>
        h1{
        font-family: 'Londrina Outline', system-ui;
        font-size: 50px;
        font-weight: lighter;
    }
    .shadowedbox{
        justify-items: left;
    }
</style>