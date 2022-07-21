<script>
	export let category;

	/* x: https://svelte.dev/repl/9bb6089d0ff545c1b34e1447fae890fd?version=3.46.4 */
	/* bind:this={pick}: svelte.dev/tutorial/classes */

	let columns = [
		{
			"name": "item",
			"cn": "w-60 pv3 pl2 pl3-l",
		},
		{
			"name": "volume",
			"cn": "w-25 pv3",
		},
		{
			"name": "price",
			"cn": "w-20 pv3",
		}
	];

	let pick;

	let array = category;

	// Holds table sort state.
	// Initialized to reflect table sorted by id column ascending.
	let sortBy = {col: "id", ascending: true};

	$: sort = (column) => {

		if (sortBy.col == column) {
			sortBy.ascending = !sortBy.ascending
		} else {
			sortBy.col = column
			sortBy.ascending = true
			// add classname: `pick` class:pick={sort === 'item'}
		}

		// Modifier to sorting function for ascending or descending
		let sortModifier = (sortBy.ascending) ? 1 : -1;

		let sort = (a, b) =>
			(a[column] < b[column])
			? -1 * sortModifier
			: (a[column] > b[column])
			? 1 * sortModifier
			: 0;

		array = array.sort(sort);
	}

	import ListItem from "./ListItem.svelte"


	$: value = $searchStore;

	//export let search;
	import { searchStore } from './stores'

</script>

<!-- /* cancel: css-tricks.com/webkit-html5-search-inputs/ */ -->
<div class="w-100 mid-gray" style="background-color: rgba(250, 250, 224, 0.8)">
	<ul class="flex list pl0 bg-lemon mv0">
		{#each columns as {name, cn}}
			<span
				class="{cn} pointer ttu"
				class:pick="{name == pick}"
				on:click={() => pick = name}
				on:click={sort(`${name}`)}
			>
				{name}
			</span>
		{/each}
	</ul>
	<ul class="list pl0 mv0">
		{#each array as row }
		<ListItem
							item={row.item}
							portions={row.volume}
							price={row.price}
							revealed={ !value || row.item.toLowerCase().match(value.toLowerCase()) || row.volume.toLowerCase().match(value.toLowerCase()) || row.price.toString().match(value.toString()) ? true : false }
							/>
		{/each}
	</ul>
</div>

<style>
.pick {
	color: black;
	text-decoration: underline;
	}
</style>