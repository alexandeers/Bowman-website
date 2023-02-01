<script setup>

</script>

<template>
    <nav class="navbar">
        <ul>
            <li><p>Home</p></li>
            <li><p>About</p></li>
            <li><p>Leaderboard</p></li>
            <li><p>Contact</p></li>
        </ul>
    </nav>
</template>

<style scoped>
nav {
    margin-block: auto;
    display: flex;
    flex-direction: column;
    place-content: center;
}

ul {
    display: flex;
    flex-direction: column;
    flex-flow: column;
    gap: 0em;
    list-style-type: none;
    padding: 0;
    transition: 200ms cubic-bezier(0.075, 0.82, 0.165, 1);
}

li {
    padding-inline: 1em;
    padding-block: 0.25em;

    flex-basis: 3em;

    transition: 500ms cubic-bezier(0.075, 0.82, 0.165, 1);
    cursor: pointer;

    display: flex;

    justify-content: center;
    /* align-items: center; */
}

li:hover {
    background: #111111;
    flex-basis: 4.5em;
}

li:hover p {
    color: var(--color-text);
    background: #111111;
    font-weight: 600;
}

p {
    font-weight: 600;
    text-transform: uppercase;
    font-size: 1.2rem;
    outline: 2px solid var(--color-text);
    background: var(--color-text);
    width: 100%;
    transition: 500ms cubic-bezier(0.075, 0.82, 0.165, 1);
    
    margin-left: 0 !important;
    padding-left: 0.25em;
    padding-right: 0.75em;
    padding-block: auto;
    color: var(--color-background);
    border-top-right-radius: 0.2em;
    border-bottom-right-radius: 0.2em;
}

</style>