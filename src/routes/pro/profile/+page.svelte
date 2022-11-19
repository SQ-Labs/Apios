<svelte:head>
	<title>Profil</title>
	<meta name="description" content="Profil d'un patient" />
</svelte:head>

<script>
	let age = 0;
	let weight = 0;
	let height = 0;
	let sys = 0;
	let dia = 0;
	let chol = 0;

	let cypheredValues = {};
	let values = {};

	let result = {};
	let decyphered = {};

	function cypher() {
		console.log(age, weight, height, sys, dia, chol);

		fetch('http://localhost:5000/cypher?age=' + age + '&weight=' + weight + '&height=' + height + '&sys=' + sys + '&dia=' + dia + '&chol=' + chol)
			.then(response => response.json())
			.then(data => {
				console.log(data);
				values = data;

				for (const [key, value] of Object.entries(data)) {
					cypheredValues[key] = value.substr(0, 100) + '...';
				}
			});
	}


	function send() {
		console.log(values);

		fetch('http://localhost:5000/compute', {
			method: 'POST',
			headers: {
				'Content-Type': 'application/json'
			},
			body: JSON.stringify(values)
		})
			.then(response => response.json())
			.then(data => {
				console.log(data);
				result = data;
			});
	}

	function decypher() {
		console.log(result);

		fetch('http://localhost:5000/decypher_result', {
			method: 'POST',
			headers: {
				'Content-Type': 'application/json'
			},
			body: JSON.stringify(result)
		})
			.then(response => response.json())
			.then(data => {
				console.log(data);
				decyphered = data;
			});
	}
</script>

<h1>BJARSTAL Georgia</h1>

<div class="parent_div">
<div class="child_div_1">
	<h2>Profil</h2>
	<p>Nom: BJARSTAL</p>
	<p>Prénom: Georgia</p>
	<p>Sexe: Femme</p>
	<p>Date de naissance: 1999-09-19</p>
	<p>N secu: X XX XX XX XXX XXX XX</p>
	<p>Adresse: 1 rue de la Paix</p>
	<p>Code postal: 75000</p>
	<p>Ville: Paris</p>
	<p>Telephone: 0123456789</p>
	<p>Email: georgia.bjarstal@epita.fr</p>
	<a href="/pro/profile/results">
	<h2>Résultats</h2>
	</a>
	<a href="/pro/profile">
	<h2>Charger des documents</h2>
	</a>
	<a href="/pro/profile">
	<h2>Renseigner des données</h2>
	</a>
	<a href="/pro/profile">
	<h2>Historique</h2>
	</a>
	<a href="/pro/profile">
	<h2>Générer un mot de passe</h2>
	</a>
</div>

<div class="child_div_2">
	<div class="text-column">
		<h2>Donnees</h2>
		<label>Age</label>
		<input bind:value={age} type="number" placeholder="Age" />
		<label>Poids</label>
		<input bind:value={weight} type="number" placeholder="Poids" />
		<label>Taille</label>
		<input bind:value={height} type="number" placeholder="Taille" />
		<label>Tension systolique</label>
		<input bind:value={sys} type="number" placeholder="Pression sanguine systolique" />
		<label>Tension diastolique</label>
		<input bind:value={dia} type="number" placeholder="Pression sanguine diastolique" />
		<label>Cholestérol</label>
		<input bind:value={chol} type="number" placeholder="Cholestérol" />
		<button on:click={cypher}>Chiffrer</button>
		<!-- <button>Envoyer</button> -->
	</div>
</div>
</div>

<pre>
	<code>
{JSON.stringify(cypheredValues, null, 2)}
	</code>
</pre>

<button on:click={send}>Envoyer</button>

<pre>
	<code>
{JSON.stringify(result, null, 2)}
	</code>
</pre>

<button on:click={decypher}>Decypher</button>

<pre>
	<code>
{JSON.stringify(decyphered, null, 2)}	
	</code>
</pre>

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
	max-width: 33vw;
}
</style>
