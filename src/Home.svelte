<script lang="ts">
    let selected = "home";
    let selectedCard: number;
</script>

<div class="container">
    <div class="top">
        <h1>START<br />PRACTICE</h1>
        <button class="button">CONTINUE</button>
        <div class="quote">
            AN IDIOT WHO PRACTICES CAN BEAT A GENIUS WHO DOESN’T.
        </div>
    </div>

    <div class="separator-container">
        <div class="separator"></div>
    </div>

    <div class="navbar">
        <button
            class:active={selected === "home"}
            on:click={() => (selected = "home")}>🏠</button
        >
        <button
            class:active={selected === "add"}
            on:click={() => (selected = "add")}>➕</button
        >
        <button
            class:active={selected === "rocket"}
            on:click={() => (selected = "rocket")}>🚀</button
        >
        <button
            class:active={selected === "settings"}
            on:click={() => (selected = "settings")}>⚙️</button
        >
    </div>
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        height: 844px;
        width: 390px;
        background: #1c1f26;
    }

    .top {
        flex: 1;
        padding: 2rem;
        border: 2px solid #00ff66;
        font-family:
            JetBrains Mono,
            monospace;
    }
    .button {
        background: #00cc66;
        color: black;
        font-weight: bold;
        border: none;
        padding: 0.8rem 2rem;
        font-size: 1rem;
        margin: 1.5rem 0;
        cursor: pointer;
    }
    .quote {
        font-size: 0.9rem;
        color: #00ff66;
    }
    .scroll-section {
        margin: 20px;
        row-gap: 20px;
        display: flex;
        flex-direction: column;
    }

    .cards {
        background: #4a6fa5;
        padding: 1.5rem;
        color: white;
        display: flex;
        justify-content: space-between;
        align-items: center;
        transition: height 0.3s ease;
        height: 57px;
        cursor: pointer;
    }

    .cards.expanded {
        height: 150px;
    }
    .card img {
        width: 50px;
        height: 50px;
    }
    .card-title {
        font-size: 1.2rem;
        font-weight: bold;
    }
    .navbar {
        display: flex;
        /*justify-content: space-around;*/
        flex-direction: row;
        align-items: center;
        align-content: stretch;
        justify-content: space-around;
        background: #21252d;
        border: 3px solid #4a6fa5ff;
        height: 80px;
    }

    .navbar > button {
        flex: 1;
    }
    .navbar button {
        border: none;
        color: #888;
        font-size: 1.5rem;
        background: #21252d;

        height: 80px;
        /*width: 96px;*/
    }
    .navbar button.active {
        color: #00ff66;
        background: #00ff66;
        height: 100%;
        border: none;
        /*width: 96px;*/
    }

    .separator {
        width: 286px;
        height: 5px;
        border-radius: 17px 17px 17px 17px;
        background: #4a6fa5ff;
    }

    .separator-container {
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 10px;
        margin-bottom: 10px;
    }
</style>
