<script>
	/* from: progressivewebninja.com/how-to-use-svelte-each-block-to-render-arrays/ */
  export let revealed;
	export let item;
	export let portions;
	export let price;

	// export let category; // category={item.category}
</script>

	<li class="flex mid-gray hover-bg-lemon default { revealed ? 'revealed' : '' }">
		<span class="w-60 pv2 pl2 pl3-l">{item}</span>
		<span class="w-25 pv2">{portions}</span>
		<span class="w-20 pv2">£{price.toFixed(2)}</span>
	</li>


<style>
	/* fix: paint/reflow performance: css-tricks.com/almanac/properties/t/transition/ */


/* faster: stackoverflow.com/questions/29229523/how-and-why-to-use-display-table-cell-css */
/* consider: stackoverflow.com/questions/29786230/how-to-create-css3-bounce-effect */
/* learn: will using `transform: translate(var)` debounce the transition? codepen.io/inspiredlabs/pen/abqKLVx */
	li {
		cursor: default; /* all: w3schools.com/csSref/tryit.asp?filename=trycss_cursor */
		visibility: hidden;
		opacity:0.1;
		max-height: 0;
		overflow: hidden;
		transition:
			max-height 666ms 0s ease,
			opacity 558ms 108ms ease,
			background-color 0.4s ease 0s;
	}
	.revealed {
		opacity:1;
		max-height: 9999px;
		visibility: visible;
	}
</style>