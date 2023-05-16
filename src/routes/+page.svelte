<script lang="ts">
    let color: string = "";
    let backgroundcolor: string = "";
    let sizes: Array<string> = ["tiny", "scriptsize", "footnotesize", "small", "normalsize", "large", "Large", "LARGE", "huge", "Huge"]; 
    let size: string = "";
    let result = `\\${size} \\color{${color}} \\colorbox{${backgroundcolor}} { text }`;
    $: result = `\\${size} \\color{${color}} \\colorbox{${backgroundcolor}} { text }`;
</script>

<style>
    * {
        padding: 0;
        margin: 0;
        border: 0;
        display: block;
    }

    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 1rem; 
    }

    select {
        border: 3px solid black;
        border-radius: 10%;
    }
</style>

<div class="container">
    <p> Text Color </p>
    <input type="color" bind:value={color} />
    
    <p> Background Color </p>
    <input type="color" bind:value={backgroundcolor} />
    
    <p> Size </p>
    <select bind:value={size}> 
        {#each sizes as i}
            <option value={i}>
                {i}
            </option>
        {/each}
    </select>


    <p>Result:</p>
    <code>{result}</code>
</div>



