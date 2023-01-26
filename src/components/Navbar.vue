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
    gap: 2em;
    list-style-type: none;
    padding: 0;
    transition: 200ms cubic-bezier(0.075, 0.82, 0.165, 1);
}

li {
    background: var(--color-text);

    outline: 2px solid var(--color-text);
    padding-inline: 1em;
    padding-block: auto;

    flex-basis: 2.75em;

    transition: 400ms cubic-bezier(0.075, 0.82, 0.165, 1);
    cursor: pointer;

    display: flex;
}

li:hover {
    background: #111111;
    flex-basis: 3.25em;
}

li:hover p {
    color: var(--color-text);
    font-weight: 600;
}

p {
    font-weight: 600;
    text-transform: uppercase;
    font-size: 1.2rem;
    margin: auto;
    margin-left: 0 !important;

    transition: 200ms cubic-bezier(0.075, 0.82, 0.165, 1);

    color: var(--color-background);
}

</style>