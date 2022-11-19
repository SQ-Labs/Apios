<script>
import Header from './Header.svelte';
import './styles.css';
</script>

<div class="app">
    <Header />

    <main>
        <slot />
    </main>

    <footer>
        <p>Developpé par <a href="https://www.aureleoules.com/" target="_blank" rel="noopener noreferrer">Aurèle</a>, <a href="https://www.georgiabjarstal.com" target="_blank" rel="noopener noreferrer">Georgia</a>, <a href="https://github.com/Yamidea" target="_blank" rel="noopener noreferrer">Marie</a> et <a href="https://www.stephanegelibert.com" target="_blank" rel="noopener noreferrer">Stéphane</a> dans le cadre d'un hackathon <a href="https://www.gottagohack.fr/" target="_blank" rel="noopener noreferrer">GGH</a></p>
    </footer>
</div>

<style>
.app {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}

main {
    flex: 1;
    display: flex;
    flex-direction: column;
    padding: 1rem;
    width: 100%;
    max-width: 64rem;
    margin: 0 auto;
    box-sizing: border-box;
}

footer {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 12px;
}

footer a {
    font-weight: bold;
}

@media (min-width: 480px) {
    footer {
        padding: 12px 0;
    }
}
</style>
