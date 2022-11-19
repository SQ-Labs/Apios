<script>
// @ts-nocheck
    export let lastname;
    export let firstname;
    export let birthdate;
    export let sexe;
    export let socialsecuritynumber;
</script>
<a href="/pro/profile">
<div class="patient">
    <p>{lastname.toUpperCase()}</p>
    <p>{firstname.charAt(0).toUpperCase() + firstname.slice(1).toLowerCase()}</p>
    <p>{birthdate}</p>
    <p>{sexe}</p>
    <p>{socialsecuritynumber}</p>
</div>
</a>

<!-- <div class="patient"> -->
<style lang="scss">
    .patient {
        display: grid;
        grid-template-columns: 2fr 2fr 2fr 0.5fr 2fr;
        grid-gap: 1rem;
        margin: 1rem;
        padding: 1rem;
        background-color: white;
        border-radius: 0.5rem;
    }
</style>