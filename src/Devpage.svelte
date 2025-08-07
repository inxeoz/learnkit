<script lang="ts">
    let selectedCard: number;
</script>

<style>
    .container {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        height: 844px;
        width: 390px;
        background: #1c1f26;
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

    .scroll-section {
        margin: 20px;
        row-gap: 20px;
        display: flex;
        flex-direction: column;
    }

    .cards {
        background: #4a6fa5;;
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
        border: 3px solid #4a6fa5FF;
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
        color: #00ff66;
        background: #00ff66;
    }

    .separator {
        width: 286px;
        height: 5px;
        border-radius: 17px;
        background: #4a6fa5FF;
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

<div class="container">

    <div class="scroll-section">
        {#each [1, 2, 3, 4] as id (id)}
            <div
                    class="cards {selectedCard === id ? 'expanded' : ''}"
                    style="background-color: {id === 1 ? '#5b3b36' : '#1a3c65'}"
                    on:click={() => selectedCard = selectedCard === id ? -1 : id}
            >
                <div class="card-title">{id === 1 ? 'RUST\nLANG' : 'DSA'}</div>
                <img src={id === 1
					? 'https://www.rust-lang.org/static/images/rust-logo-blk.svg'
					: 'https://upload.wikimedia.org/wikipedia/commons/3/35/Tux.svg'}
                     alt="icon"
                />
            </div>
        {/each}
    </div>

    <div class="separator-container">
        <div class="separator"></div>
    </div>

    <div class="center">
        <button class="button">ADD NEW</button>
    </div>

    <div class="navbar">
        <button class:active={selectedCard === 100} on:click={() => selectedCard = 100}>🏠</button>
        <button class:active={selectedCard === 101} on:click={() => selectedCard = 101}>➕</button>
        <button class:active={selectedCard === 102} on:click={() => selectedCard = 102}>🚀</button>
        <button class:active={selectedCard === 103} on:click={() => selectedCard = 103}>⚙️</button>
    </div>
</div>
