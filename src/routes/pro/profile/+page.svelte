<svelte:head>
	<title>Profile</title>
	<meta name="description" content="Profil d'un patient" />
</svelte:head>

<script>
</script>

<h1>BJARSTAL Georgia</h1>

<div class="parent_div">
<div class="child_div_1">
	<h2>Profil</h2>
	<p>Nom: BJARSTAL</p>
	<p>Prenom: Georgia</p>
	<p>Sexe: Femme</p>
	<p>Date de naissance: 1999-09-19</p>
	<p>N secu: X XX XX XX XXX XXX XX</p>
	<p>Adresse: 1 rue de la Paix</p>
	<p>Code postal: 75000</p>
	<p>Ville: Paris</p>
	<p>Telephone: 0123456789</p>
	<p>Email: georgia.bjarstal@epita.fr</p>
	<a href="/">
	<h2>Charger des documents</h2>
	</a>
	<a href="/">
	<h2>Historique</h2>
	</a>
	<a href="/">
	<h2>Générer un mot de passe</h2>
	</a>
</div>

<div class="child_div_2">
	<div class="text-column">
		<h2>Donnees</h2>
		<input type="number" placeholder="Poids" />
		<input type="number" placeholder="Taille" />
		<input type="number" placeholder="Pression sanguine systolique" />
		<input type="number" placeholder="Pression sanguine diastolique" />
		<input type="number" placeholder="Cholestérol" />
		<button>Enregistrer</button>
		<button>Envoyer</button>
	</div>
</div>
</div>

<style>
.parent_div {
    width: fit-content;
    height: fit-content;
    margin-right: 10px;
    float: left;
}

.child_div_1 {
    float: left;
    margin-right: 5px;
    padding: 1rem;
    background-color: white;
    border-radius: 1rem;
}

.child_div_2 {
    float: right;
    margin-left: 5px;
    padding: 1rem;
    background-color: white;
    border-radius: 1rem;
}
</style>
