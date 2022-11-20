<svelte:head>
	<title>Pro</title>
	<meta name="description" content="Version professionnelle" />
</svelte:head>

<script>
let login = ""
let password = ""
</script>

<div class="text-column">
	<h1>Bon retour parmi nous !</h1>

<input type="text" placeholder="Login" bind:value={login} />
	<input type="password" placeholder="Mot de passe" bind:value={password} />
	<a href="pro/search">

<button>Se connecter</button>
	</a>
</div>
