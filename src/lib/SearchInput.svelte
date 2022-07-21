<script>
	import { searchStore } from './stores'
	export let search;

	function all() {
		// alert('ciaonne!')
		$searchStore = '';
	}
</script>

<input
id="filter"
type="search"
bind:value={$searchStore}
placeholder="Search"
bind:this={search}
class="input-reset pa3 bn f4"
><button on:click|preventDefault={ all } class="input-reset pa3 f4 bn bg-near-black hover-bg-red transition white">&#10005;</button>
<!-- <label for="filter" class="h3">{$searchStore}</label> -->

<style>
input[type="search"]::-webkit-search-decoration,
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-results-button,
input[type="search"]::-webkit-search-results-decoration { display: none; }
</style>