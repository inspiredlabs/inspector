<script>

/********* Filter *********/
import SearchInput from "$lib/SearchInput.svelte";
import Filter from '$lib/Filter.svelte';
import { dips } from '$lib/dips.js';
import { smallPots } from '$lib/smallPots.js';
import { pesto } from '$lib/pesto.js';
import { dairy } from '$lib/dairy.js';
import { meat } from '$lib/meat.js';
import { cheeses } from '$lib/cheeses.js';
import { oils } from '$lib/oils.js';
import { breads } from '$lib/breads.js';
import { tins } from '$lib/tins.js';
import { mixedMarinatedVeg } from '$lib/mixedMarinatedVeg.js';
import { olives } from '$lib/olives.js';
import { bakery } from '$lib/bakery.js';
import { cheesecakes } from '$lib/cheesecakes.js';
import { patisseries } from '$lib/patisseries.js';
import { flapjacks } from '$lib/flapjacks.js';
import { trays } from '$lib/trays.js';
/********* Filter *********/

import Row from '$lib/Row.svelte';

</script>

<Row bg="pa0 ma0 fixed system ">
	<SearchInput />
</Row>

<!-- <Row bg="pa0 ma0 fixed verdana">
<nav
	class="w-100 z-1 pt4 flex flex-nowrap flex-row justify-around landscape-dn" style="pointer-events:none">
	<a
		style="pointer-events:auto;line-height:4rem"
		href="https://wa.me/447426646183/?text=I%27d%20like%20to%20order..."
		class="
		link
		pv2
		ph3
		pointer hover-white transition
		bn bg-whatsapp
		f3 tc mercury white-80 ts1-dark-gray"
		>Whatsapp</a>

	<a
		style="pointer-events:auto;line-height:4rem"
		href='tel:+447426646183'
		class="
		link
		pv2
		ph3
		pointer hover-white transition
		bn bg-oxford
		f3 tc mercury white-60 ts1-dark-gray"
		>Mobile</a>
	</nav>
</Row> -->

<Row bg="mv5 pv5 verdana mid-gray">

	<h3 class="bg-lemon mv0 pt5 pb0 ph2 ph3-l mid-gray ttu">Dips</h3>
	<Filter category={dips} />

	<h3 class="bg-lemon mv0 pt5 pb0 ph2 ph3-l mid-gray ttu">Small Pots</h3>
	<Filter category={smallPots} />

	<h3 class="bg-lemon mv0 pt5 pb0 ph2 ph3-l mid-gray ttu">Pesto</h3>
	<Filter category={pesto} />

	<h3 class="bg-lemon mv0 pt5 pb0 ph2 ph3-l mid-gray ttu">Dairy, Meats &amp; Cheeses</h3>
	<Filter category={dairy} />
	<Filter category={meat} />
	<Filter category={cheeses} />

	<h3 class="bg-lemon mv0 pt5 pb0 ph2 ph3-l mid-gray ttu">Oils &amp; Breads</h3>
	<Filter category={oils} />
	<Filter category={breads} />

	<h3 class="bg-lemon mv0 pt5 pb0 ph2 ph3-l mid-gray ttu">Tinned Foods</h3>
	<Filter category={tins} />

	<h3 class="bg-lemon mv0 pt5 pb0 ph2 ph3-l mid-gray ttu">Mixed Marinated Vegetables </h3>
	<Filter category={mixedMarinatedVeg} />

	<h3 class="bg-lemon mv0 pt5 pb0 ph2 ph3-l mid-gray ttu">Olives</h3>
	<Filter category={olives} />

	<h3 class="bg-lemon mv0 pt5 pb0 ph2 ph3-l mid-gray ttu">Bakery</h3>
	<Filter category={bakery} />
	<Filter category={cheesecakes} />
	<Filter category={patisseries} />
	<Filter category={flapjacks} />
	<Filter category={trays} />
	<hr class="h4 mv0" style="background-color: rgba(250, 250, 224, 0.8)">

</Row>











<style>

@media all and (orientation:landscape) {
	.landscape-dn {
		display: none;
	}
}


/****** $ BREAKOUT PAGINATOR COMPONENT $ *******/

	/* `overflow-x-hidden` repaints often and `.transition` has poor performance implactions so treat them as a lazy handler. `.transition-bs` or `transition-bg`, are NOT yet integrated into Tachyonshower.
	*/

	/* https://stackoverflow.com/questions/71074/how-to-remove-firefoxs-dotted-outline-on-buttons-as-well-as-links */

	a:focus {
		outline: none;
		box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.8); /* Deeper than `.shadow-5-hover` */
	}

	a::-moz-focus-inner {
		border: 0;
		box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.8); /*Deeper than `.shadow-5-hover` */
	}



	.transition-bs {
		transition: box-shadow 0.4s ease 0s;
		-webkit-transition: box-shadow 0.4s ease 0s;
	}
	.transition-bg {
		transition: background 0.4s ease 0s;
		-webkit-transition: background 0.4s ease 0s;
	}

	:root{ --tint: 0.5; /* 1 is max */ }
	/* `.mh-100-vh { max-height: 100vh }` convention borrowed: .mw-100 { max-width: 100% } and `.100-vh { height: 100vh }` */

	/* Flexbox should be preferred over conditional-css: `.zed:nth-child(3n) { margin-right: 0 }`: css-tricks.com/almanac/selectors/n/nth-child/ */


/****** ^ BREAKOUT PAGINATOR COMPONENT ^ *******/
















/* svelte.dev/repl/253993c0325a4b1b8ff38b4c4ecd2285?version=3.24.1
	- from: stackoverflow.com/questions/63315507/svelte-how-can-i-set-the-focus-to-the-previous-next-element-in-the-list-item-wh#63324281
*/

.active {
	opacity: 0.9;
}
a:focus {
	opacity: 1;
}

/* .active a img {
	background: transparent!important;
} */

/* `.hover-ltr` can not be implemented into Tachyon Shower. It's not atomic. */
	/* :global(a) {
		text-decoration: none!important
	} */
.hover-ltr::after {
	position: absolute;
	left: 0;
	content: '';
	width: 100%;
	height: 8%;
	background: currentColor;
	bottom: 0;
	transform: scale(0, 1);
	transition: transform 0.4s;
	transform-origin: right top;
}
.hover-ltr:hover::after {
	transform-origin: left top;
	transform: scale(1, 1);
}
/*** simplify this ***/
.debug * {
	outline: 1px solid lime;
}
@media screen and (min-width: 30em) {
	.debug * {
		outline: 1px solid goldenrod;
	}
}
@media screen and (min-width: 30em) and (max-width: 60em) {
	.debug * {
		outline: 1px solid firebrick;
	}
}
@media screen and (min-width: 60em) {
	.debug * {
		outline: 1px solid cyan;
	}
}
/* amend tachyon.shower.css */
.truncate {
	display: -webkit-box;
	white-space: nowrap;
/* overflow: hidden; */
	text-overflow: ellipsis;
}
/**** snapper ****/
/* .y-mandatory {
	scroll-snap-type: y mandatory;
} */
/* .y-proximity {
	scroll-snap-type: y proximity;
} */
/* .snapper {
	padding-top:15vh;
	padding-bottom:0vh;
	scroll-margin: 20vh;
	scroll-snap-align: start;
	scroll-snap-stop: normal;
} */
:root {
	--time: 0.6s
}
/* https://css-tricks.com/almanac/properties/w/will-change/ */
/* .minno {
	will-change: transform, scroll-position;
	-moz-osx-font-smoothing: grayscale;
	-webkit-backface-visibility: hidden;
	backface-visibility: hidden;
	-webkit-transform: translateZ(0);
	transform: translateZ(0);
	transition: -webkit-transform var(--time) ease;
	transition: all var(--time) ease;
	transition: all var(--time) ease,
	-webkit-transform var(--time) ease;
	background-clip: padding-box;
	box-shadow: 0 0 0 0 rgba(0, 0, 0, 0);
}
.minno:focus,
.minno:hover {
	-webkit-transform: perspective(1px) scale(1.008);
	transform: perspective(1px) scale(1.008);
	box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.1);
}
.minno:active {
	-webkit-transform: perspective(1px) scale(1.02);
	transform: perspective(1px) scale(1.02);
	box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.1);
}
*/
/* HTML: w-100 h-100 system */
@media all and (orientation:portrait) {
/*   .portrait-dn {
		display: none;
	} */
/*   .portrait-vh-50 {
	height: 50vh;
	} */
	@media screen and (min-width:30em) {
/*     .portrait-dn-ns {
			display: none;
		} */
/*     .portrait-vh-85-ns {
		height: 85vh;
		} */
		.portrait-bottom-0-ns {
		bottom: 0;
		}
	}
	@media screen and (min-width:30em) and (max-width:60em) {
/*     .portrait-dn-m {
			display: none;
		} */
/*     .portrait-vh-85-m {
		height: 85vh;
		} */
		.portrait-bottom-0-m {
		bottom: 0;
		}
	}
	@media screen and (min-width:60em) {
/*     .portrait-dn-l {
			display: none;
		} */
		.portrait-bottom-0-l {
		bottom: 0;
		}
	}
}
@media all and (orientation:landscape) {
/*   .landscape-db {
			display: block;
		} */
/*   .landscape-dn {
		display: none;
	} */
/*   .landscape-vh-66 {
	height: 66vh;
	} */
	@media screen and (min-width:30em) {
/*     .landscape-vh-85-ns {
		height: 85vh;
		} */
/*     .landscape-db-ns {
			display: block;
		} */
/*     .landscape-dn-ns {
			display: none;
		} */
	}
	@media screen and (min-width:30em) and (max-width:60em) {
/*     .landscape-vh-66-m {
		height: 66vh;
		} */
/*     .landscape-db-m {
			display: block;
		} */
/*     .landscape-dn-m {
			display: none;
		} */
	}
	@media screen and (min-width:60em) {
/*     .landscape-vh-85-l {
		height: 85vh;
		} */
		.landscape-top-0-l {
		top: 0;
		}
/*     .landscape-db-l {
			display: block;
		} */
		.landscape-dn-l {
			display: none;
		}
		.landscape-flex-l {
			display: flex;
		}
	}
}
:global(html, body) { padding: 0 }
/* Hide scrollbar for Chrome, Safari and Opera
main::-webkit-scrollbar {
	display: none;
}*/
/* Hide scrollbar for IE, Edge and Firefox
main {
	-ms-overflow-style: none;  /* IE and Edge
	scrollbar-width: none;  /* Firefox
}
*/

.backdrop-blur { backdrop-filter: blur(8px) } /* from: `offline`:  localhost:3000/viaggi */
</style>