<script>
    import {createEventDispatcher} from 'svelte';
    let name;
    let beltcolour;
    let age;

    let skills = [];

    const dispatcher = createEventDispatcher();

    const submitHandler = () => {
        let person = {
            name,
            beltcolour,
            age,
            skills,
            id: Math.random() 
        }
        console.log(person);
        dispatcher('addPerson', person);
    }
</script>

<form on:submit|preventDefault={submitHandler}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="number" placeholder="age" bind:value={age}>
    <button>Add Person</button>
    <input type="checkbox" bind:group={skills} value="fighting"/> fighting
    <input type="checkbox" bind:group={skills} value="running"/> running
    <input type="checkbox" bind:group={skills} value="jumping"/> jumping
    <select bind:value={beltcolour}>
        <option value="black">black</option>
        <option value="orange">orange</option>
        <option value="brown">brown</option>
        <option value="yellow">yellow</option>
    </select>
</form>