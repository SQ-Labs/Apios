<script>
import Patient from "./Patient.svelte";
</script>

<div class="text-column">
	<h1>Résultats</h1>
	<div class="create-button">
	<a href="/pro/search"><button>Créer un patient</button></a>
	</div>
	<Patient lastname="BJARSTAL" firstname="GeOrGiA" birthdate="19/09/1999" sexe="F" socialsecuritynumber="X XX XX XX XXX XXX XX"/>
	<Patient lastname="Dumestre" firstname="Marie" birthdate="14/02/2000" sexe="F" socialsecuritynumber="XX XX XX XX XXX XXX XX"/>
	<Patient lastname="garrido" firstname="lorine" birthdate="06/03/1999" sexe="F" socialsecuritynumber="XX XX XX XX XXX XXX XX"/>
	<Patient lastname="Gélibert" firstname="Stéphane" birthdate="28/03/2000" sexe="M" socialsecuritynumber="XX XX XX XX XXX XXX XX"/>
	<Patient lastname="Oulès" firstname="Aurèle" birthdate="30/05/2001" sexe="M" socialsecuritynumber="XX XX XX XX XXX XXX XX"/>
	<Patient lastname="trodet" firstname="charles" birthdate="17/05/2000" sexe="M" socialsecuritynumber="XX XX XX XX XXX XXX XX"/>
</div>

<style lang="scss">
	.create-button {
		align-content: center;
		align-items: center;
		padding: 1rem;
	}
</style>