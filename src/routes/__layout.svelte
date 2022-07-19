<script lang="ts">
	// import Header from '$lib/Header/index.svelte';
	import ReloadPrompt from '$lib/ReloadPrompt/index.svelte';
	import '../app.css';
</script>
<!-- <Header /> -->


	<main class="w-100 h-100 overflow-x-scroll ">
		<slot></slot>
	</main>


<ReloadPrompt />

<style>
:global(.verdana) {
font-family: Verdana, Geneva, sans-serif;
}

/* learn: see how `mid-gray` interacts with `bg-lemon` contrast-ratio.com/ */

:global(.mid-gray) {
color: #666;
}

:global(.bg-lemon) {
background-color: hsla(60,71%,93%,1);
}

:global(.hover-bg-lemon:hover),
:global(.hover-bg-lemon:focus) {
background-color: hsla(60,71%,93%,0.6);
}

:global(.bg-blur){backdrop-filter: blur(12px)}
/* Quick prune: purifycss.online/ @import '$lib/Tachyonshower'; */

:global(.snap-center) {
	scroll-snap-align: center;
}
:global(.nw-100) {
	min-width: 100%;
}

:global(.x-mandatory) {
	-webkit-overflow-scrolling: touch;
	scroll-snap-type: x mandatory;
	/* must be used with: `scroll-snap-align: center` */
}

/* :global(.x-proximity) {
	scroll-snap-type: x proximity;
} */

:global(.touch-scroll) {
	-webkit-overflow-scrolling: touch;
}
</style>

<svelte:head>
	<!-- <link rel="stylesheet" type="text/css" href="../support/css/tachyon.shower.css"> -->

	<link rel="manifest" href="/manifest.webmanifest" />
	<link rel="apple-touch-icon" href="/apple-icon-180.png" />

	<meta
		name="description"
		content="Svelte-Kit PWA"
	/>
	<meta name="apple-mobile-web-app-capable" content="yes" />
	<!-- <link rel="icon" href="/favicon.svg" type="image/svg+xml"> -->
	<link rel="apple-touch-icon" href="/pwa-192x192.png" />
	<!-- <link rel="mask-icon" href="/safari-pinned-tab.svg" color="#00aba9"> -->
	<meta name="msapplication-TileColor" content="#00aba9" />
	<meta name="theme-color" content="#ffffff" />
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-2048-2732.jpg"
		media="(device-width: 1024px) and (device-height: 1366px) and (-webkit-device-pixel-ratio: 2) and (orientation: portrait)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-2732-2048.jpg"
		media="(device-width: 1024px) and (device-height: 1366px) and (-webkit-device-pixel-ratio: 2) and (orientation: landscape)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-1668-2388.jpg"
		media="(device-width: 834px) and (device-height: 1194px) and (-webkit-device-pixel-ratio: 2) and (orientation: portrait)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-2388-1668.jpg"
		media="(device-width: 834px) and (device-height: 1194px) and (-webkit-device-pixel-ratio: 2) and (orientation: landscape)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-1536-2048.jpg"
		media="(device-width: 768px) and (device-height: 1024px) and (-webkit-device-pixel-ratio: 2) and (orientation: portrait)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-2048-1536.jpg"
		media="(device-width: 768px) and (device-height: 1024px) and (-webkit-device-pixel-ratio: 2) and (orientation: landscape)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-1668-2224.jpg"
		media="(device-width: 834px) and (device-height: 1112px) and (-webkit-device-pixel-ratio: 2) and (orientation: portrait)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-2224-1668.jpg"
		media="(device-width: 834px) and (device-height: 1112px) and (-webkit-device-pixel-ratio: 2) and (orientation: landscape)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-1620-2160.jpg"
		media="(device-width: 810px) and (device-height: 1080px) and (-webkit-device-pixel-ratio: 2) and (orientation: portrait)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-2160-1620.jpg"
		media="(device-width: 810px) and (device-height: 1080px) and (-webkit-device-pixel-ratio: 2) and (orientation: landscape)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-1284-2778.jpg"
		media="(device-width: 428px) and (device-height: 926px) and (-webkit-device-pixel-ratio: 3) and (orientation: portrait)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-2778-1284.jpg"
		media="(device-width: 428px) and (device-height: 926px) and (-webkit-device-pixel-ratio: 3) and (orientation: landscape)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-1170-2532.jpg"
		media="(device-width: 390px) and (device-height: 844px) and (-webkit-device-pixel-ratio: 3) and (orientation: portrait)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-2532-1170.jpg"
		media="(device-width: 390px) and (device-height: 844px) and (-webkit-device-pixel-ratio: 3) and (orientation: landscape)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-1125-2436.jpg"
		media="(device-width: 375px) and (device-height: 812px) and (-webkit-device-pixel-ratio: 3) and (orientation: portrait)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-2436-1125.jpg"
		media="(device-width: 375px) and (device-height: 812px) and (-webkit-device-pixel-ratio: 3) and (orientation: landscape)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-1242-2688.jpg"
		media="(device-width: 414px) and (device-height: 896px) and (-webkit-device-pixel-ratio: 3) and (orientation: portrait)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-2688-1242.jpg"
		media="(device-width: 414px) and (device-height: 896px) and (-webkit-device-pixel-ratio: 3) and (orientation: landscape)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-828-1792.jpg"
		media="(device-width: 414px) and (device-height: 896px) and (-webkit-device-pixel-ratio: 2) and (orientation: portrait)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-1792-828.jpg"
		media="(device-width: 414px) and (device-height: 896px) and (-webkit-device-pixel-ratio: 2) and (orientation: landscape)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-1242-2208.jpg"
		media="(device-width: 414px) and (device-height: 736px) and (-webkit-device-pixel-ratio: 3) and (orientation: portrait)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-2208-1242.jpg"
		media="(device-width: 414px) and (device-height: 736px) and (-webkit-device-pixel-ratio: 3) and (orientation: landscape)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-750-1334.jpg"
		media="(device-width: 375px) and (device-height: 667px) and (-webkit-device-pixel-ratio: 2) and (orientation: portrait)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-1334-750.jpg"
		media="(device-width: 375px) and (device-height: 667px) and (-webkit-device-pixel-ratio: 2) and (orientation: landscape)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-640-1136.jpg"
		media="(device-width: 320px) and (device-height: 568px) and (-webkit-device-pixel-ratio: 2) and (orientation: portrait)"
	/>
	<link
		rel="apple-touch-startup-image"
		href="/apple-splash-1136-640.jpg"
		media="(device-width: 320px) and (device-height: 568px) and (-webkit-device-pixel-ratio: 2) and (orientation: landscape)"
	/>
</svelte:head>