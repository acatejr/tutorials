<script>
    let name
    let beltColour
    let age
    let skills = []

    const handleSubmit = () => {
        console.log(name, beltColour, age, skills)
    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="Name" bind:value={name}>
    <!-- <input type="text" placeholder="Belt Colour" bind:value={beltColour}> -->
    <input type="number" placeholder="Age" bind:value={age}>
    <label>Skils:</label>
    <input type="checkbox" bind:group={skills} value='fighting'>fighting<br/>
    <input type="checkbox" bind:group={skills} value='sneaking'>sneaking<br/>
    <input type="checkbox" bind:group={skills} value='running'>running<br/>
    <button>Add Person</button>
    
    <label>Belt Colour:</label>
    <select bind:value={beltColour}>
        <option value="black">black</option>
        <option value="orange">orange</option>
        <option value="brown">brown</option>
        <option value="white">white</option>
    </select>
</form>

<style></style>