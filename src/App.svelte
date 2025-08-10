<script lang="ts">
    import Home from "./Home.svelte";
    import Devpage from "./Devpage.svelte";
    import './app.css'
    import Demo from "./Demo.svelte";
</script>

<main >
    <div class="main-container">
        <Home/>
        <Devpage/>
        <Demo/>

    </div>

</main>

<style>

    .main-container {
        display: flex;
        flex-wrap: wrap;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        row-gap: 4rem;
        column-gap: 4rem;
        width: 100vw;
    }
</style>
