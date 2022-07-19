<script>
	export let category;

	let sortedData = category;
	const tableHeaders = Object.keys(category[0])
	// console.log(tableHeaders)

	let selectedHeader = "id";
	let ascendingOrder = true;

	// SORT BY NUMBER
	const sortByNumber = (colHeader) => {
		sortedData = sortedData.sort((obj1, obj2) => {
			return ascendingOrder ? Number(obj1[colHeader]) - Number(obj2[colHeader])
			: Number(obj2[colHeader]) - Number(obj1[colHeader])
		});
		selectedHeader = colHeader;
	}

	// SORT BY STRINGs
	const sortByString = (colHeader) => {
		sortedData = sortedData.sort((obj1, obj2) => {
			if (obj1[colHeader] < obj2[colHeader]) {
					return -1;
			} else if (obj1[colHeader] > obj2[colHeader]) {
				return 1;
			}
			return 0; //string code values are equal
		});
		if (!ascendingOrder) {
			sortedData = sortedData.reverse()
		}
		selectedHeader = colHeader;
	}
</script>

<!-- learn: verdana mid-gray ts1-white -->
<table class="bn collapse fw3 w-100">

  <tr class="bg-lemon fw6">
		{#each tableHeaders as header}

				<!-- learn: this is complete... -->
				<th
				class="pointer ttu pl2 pl3-l pv3
				{ header === 'id' ? 'dn' : '' }
				{ header === 'price' ? 'pr2' : '' }
				{ header === 'category' ? 'dn' : '' }"
				class:pick={selectedHeader === header}
						on:click={() => (header === "id" || header === "price" ) ? sortByNumber(header) : sortByString(header)}>
					<span
						class="pointer ttu"
						on:click={() => ascendingOrder = !ascendingOrder}>
						{header.replace("_", " ")}
					</span>
				</th>

		{/each}
  </tr>

	{#each sortedData as item}
		<tr class="hover-bg-lemon bg-transition">
			<td class="dn pv2 pl2 pl3-l">{item.id}</td>
			<td class="w-two-thirds pv2 pl2 pl3-l">{item.item}</td>
			<td class="w-25 pv2 pl2 pl3-l">{item.portions ? item.portions : item.volume}</td>
			<td class="pv2 pl2 pl3-l" style="width:4%">&pound;{item.price.toFixed(2)}</td>

			<div class="dn">
			{#if item.category === 'dips'}
				<td class="w-10 ttc bg-gold pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Small Pots'}
				<td class="w-10 ttc bg-red pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'pesto'}
				<td class="w-10 ttc bg-meadow pv2 pl2 pl3-l">{item.category}</td>

			{:else if item.category === 'Dairy'}
				<td class="w-10 ttc bg-yellow pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Meat'}
				<td class="w-10 ttc bg-yellow pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Cheeses'}
				<td class="w-10 ttc bg-yellow pv2 pl2 pl3-l">{item.category}</td>

			{:else if item.category === 'Oils, Vinegars and Breads'}
				<td class="w-10 ttc bg-electric-lime pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'seafood'}
				<td class="w-10 ttc bg-mexicano pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Vegetables, Tomatoes and crudit\u00e9'}
				<td class="w-10 ttc bg-soccorso pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Mixed Marinated Vegetables'}
				<td class="w-10 ttc bg-caribbean pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'olives'}
				<td class="w-10 ttc bg-cobalt white pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Tray Bakes'}
				<td class="w-10 ttc bg-beige pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Fresh Cream Individual Pastries'}
				<td class="w-10 ttc bg-tyrian white pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Patisserie, Pre-cut and Papered'}
				<td class="w-10 ttc bg-health pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Patisserie, Pies and Cakes'}
				<td class="w-10 ttc bg-grape white pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Patisserie, Muffins and Trays'}
				<td class="w-10 ttc bg-green white pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'American Baked Cheesecakes'}
				<td class="w-10 ttc bg-orange pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Cold Processed Cheescakes'}
				<td class="w-10 ttc bg-magnolia pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Fresh Cream Birthday Cakes. Inc. personal iced lettering'}
				<td class="w-10 ttc bg-gold pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Miscellaneous'}
				<td class="w-10 ttc bg-health pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Halva Blocks'}
				<td class="w-10 ttc bg-electric-lime pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Flapjacks and Malted Bars'}
				<td class="w-10 ttc bg-beige pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Brownies'}
				<td class="w-10 ttc bg-mustard white pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Shortbreads'}
				<td class="w-10 ttc bg-yellow pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === '10\" Round Cakes'}
				<td class="w-10 ttc bg-pink">{item.category}</td>
			{:else if item.category === '10\" Loaf Cakes'}
				<td class="w-10 ttc bg-silver pv2 pl2 pl3-l">{item.category}</td>
			{:else if item.category === 'Vegetarian Savoury Pies and Flan'}
				<td class="w-10 ttc bg-light-gray pv2 pl2 pl3-l">{item.category}</td>
			{:else}
				<td class="w-10 ttc pv2 pl2 pl3-l" style="background:cyan">{item.category}</td>
			{/if}
		</div>
	</tr>
	{/each}

</table>


<style>
	/* fix: improves performance on inital paint and reflow: css-tricks.com/almanac/properties/t/transition/ */
	.bg-transition {
		transition:  background-color 0.4s ease 0s;
	}
	table {
		/* border: 0 solid transparent; */
		background-color: rgba(250, 250, 224, 0.8)
	}

	/* color: hsl(15, 100%, 45%) */
	.pick {
		color: black;
		text-decoration: underline
	}

	th, td {
		text-align: left;
		vertical-align: top;
	}

	tr:nth-child(even) {
		/* background-color: #f2f2f2 */
	}
</style>