<script lang="ts">
    let selectedCard: number = -1;
</script>

<div class="container">
    <div class="top">
        <h1>START<br />PRACTICE</h1>
        <button class="button">CONTINUE</button>
        <div class="quote">
            AN IDIOT WHO PRACTICES CAN BEAT A GENIUS WHO DOESN’T.
        </div>
    </div>

    <div class="scroll-section">
        <div class="scroll-inner">
            {#each [1, 2, 3, 4] as id (id)}
                <div
                    class="cards"
                    class:expanded={selectedCard === id}
                    style="background-color: {id === 1 ? '#5b3b36' : '#1a3c65'}"
                    on:click={() =>
                        (selectedCard = selectedCard === id ? -1 : id)}
                >
                    <div class="card-title">
                        {id === 1 ? "RUST" : "DSA"}<br />{id === 1
                            ? "LANG"
                            : ""}
                    </div>
                    <img
                        src={id === 1
                            ? "https://www.rust-lang.org/static/images/rust-logo-blk.svg"
                            : "https://upload.wikimedia.org/wikipedia/commons/3/35/Tux.svg"}
                        alt="icon"
                    />
                </div>
            {/each}
        </div>
    </div>

    <div class="separator-container">
        <div class="separator"></div>
    </div>

    <div class="center">
        <button class="button">ADD NEW</button>
    </div>

    <div class="navbar">
        <button
            class:active={selectedCard === 100}
            on:click={() => (selectedCard = 100)}>🏠</button
        >
        <button
            class:active={selectedCard === 101}
            on:click={() => (selectedCard = 101)}>➕</button
        >
        <button
            class:active={selectedCard === 102}
            on:click={() => (selectedCard = 102)}>🚀</button
        >
        <button
            class:active={selectedCard === 103}
            on:click={() => (selectedCard = 103)}>⚙️</button
        >
    </div>
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
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

    /* FIXED HEIGHT scroll-section */
    .scroll-section {
        margin: 20px;
        height: 300px; /* visible height */
        overflow-y: auto;
        flex-shrink: 0;
    }

    /* VIRTUAL height for internal content */
    .scroll-inner {
        display: flex;
        flex-direction: column;
        row-gap: 20px;
        min-height: 500px; /* gives space for expansion */
    }

    .cards {
        padding: 1.5rem;
        color: white;
        display: flex;
        justify-content: space-between;
        align-items: center;
        transition: height 0.3s ease;
        height: 57px;
        cursor: pointer;
        overflow: hidden;
    }

    .cards.expanded {
        height: 250px; /* expanded card height */
    }

    .cards img {
        width: 50px;
        height: 50px;
    }

    .card-title {
        font-size: 1.2rem;
        font-weight: bold;
    }

    .navbar {
        display: flex;
        justify-content: space-around;
        background: #21252d;
        border: 3px solid #4a6fa5ff;
        height: 80px;
    }

    .navbar > button {
        flex: 1;
        border: none;
        color: #888;
        font-size: 1.5rem;
        background: #21252d;
        height: 80px;
        cursor: pointer;
    }

    .navbar button.active {
        color: #1c1f26;
        background: #00ff66;
    }

    .separator {
        width: 286px;
        height: 5px;
        border-radius: 17px;
        background: #4a6fa5ff;
    }

    .separator-container {
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 10px 0;
    }

    .center {
        display: flex;
        justify-content: center;
    }
</style>
