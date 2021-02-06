<script>
    import { createEventDispatcher } from 'svelte'

    let dispatch = createEventDispatcher()

    let name
    let beltColour
    let age
    let skills = []

    const handleSubmit = () => {
        const person = {
            name: name,
            beltColour: beltColour,
            age: age,
            skills: skills,
            id: Math.random()
        }

        dispatch('addPerson', person)
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
    
    <label>Belt Colour:</label>
    <select bind:value={beltColour}>
        <option value="black">black</option>
        <option value="orange">orange</option>
        <option value="brown">brown</option>
        <option value="white">white</option>
    </select>
    <button>Add Person</button>
</form>

<style></style>