<script>
    // let projects = $state(['Sweater', 'Hat'])
    // let newProject = $state();
    let {projects} = $props()
</script>

<div style="display:flex; flex-direction:column">
    {#each projects as project }
        <label>
            <input type="checkbox"/>
            {project.name}
        </label>
        <details>
            <summary>more info</summary>
            <p>
                hook size: {project.hook}
                pattern: {project.pattern}
            </p>
        </details>
    {/each}
    </div>

<style>

</style>