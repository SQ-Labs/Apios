<svelte:head>
	<title>Pro Dashboard</title>
	<meta name="description" content="Dashboard Pro" />
</svelte:head>

<script>
import {
    onMount
} from 'svelte';

let now = new Date(),
    month, day, year;
/**
 * @type {string}
 */
let dateString;

onMount(() => {
    month = '' + (now.getMonth() + 1),
        day = '' + now.getDate(),
        year = now.getFullYear();

    if (month.length < 2)
        month = '0' + month;
    if (day.length < 2)
        day = '0' + day;

    dateString = [year, month, day].join('-');
})

let questions = [{
        id: 1,
        text: `Femme`
    },
    {
        id: 2,
        text: `Homme`
    },
];

/**
 * @type {{ id: any; text: any; }}
 */
let selected;
let answer = '';

function handleSubmit() {
    alert(`answered question ${selected.id} (${selected.text}) with "${answer}"`);
}
</script>

<div class="text-column">
	<h1>Rechecher un patient </h1>
	<input type="text" placeholder="Nom" />
	<input type="text" placeholder="Nom de jeune fille" />
	<input type="text" placeholder="Prénom" />
	<input type="number" placeholder="Numero de securite social" />
	<input type=date bind:value={dateString}>
	<select value={selected} on:change="{() => answer = ''}">

{#each questions as question}

<option value={question}>

{question.text}

</option>

{/each}
	</select>

<a href="search/results">
	<button>Rechercher</button>
	</a>
</div>
