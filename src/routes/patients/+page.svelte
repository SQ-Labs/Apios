<svelte:head>
	<title>Pro</title>
	<meta name="description" content="Version professionnelle" />
</svelte:head>

<script>
let num_secu = ""
let password = ""
</script>

<div class="text-column">
	<h1>Patients</h1>

	<input type="number" placeholder="Numéro de sécurité social" bind:value={num_secu} />
	<input type="password" placeholder="Mot de passe" bind:value={password} />
	<a href="patients/ma_fiche">
		<button>Se Connecter</button>
	</a>

	<h2>Je n'ai pas de mot de passe</h2>
	<p>L'obtention du mot de passe se fait a l'accueil du centre medical qui vous a accueilli.</p>
</div>
