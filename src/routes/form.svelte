<script context="module" lang="ts">
	export const prerender = true;
</script>
<!-- <script lang="ts"></script> -->
<script>
let form;
let submitted = false;
let isSubmitting = false;
let status = "It works!";

async function handleSubmit(event) {

	var data = new FormData(event.target);

	isSubmitting = true;

	fetch(event.target.action, {
		method: form.method,
		body: data,
		headers: {
			'Accept': 'application/json'
	}
		}).then(() => {
			// note: do something:
			console.log("Form submitted!");
			submitted = true;
			isSubmitting = false;
		})
		.finally(() => {
			// note: do something:
			console.log("It works!");
			// xxx
			form.reset();
		})
		.catch((error) => {
			console.log(error);
			isSubmitting = false;
		});
	}

</script>

<section>
	<h1>Formspree</h1>

	<form
		bind:this={form}
		on:submit|preventDefault={handleSubmit}
		action="https://formspree.io/&#102;&sol;&#109;&#113;&#107;&#110;&#111;&#114;&#100;&#100;"
		method="POST"
		class="w-100 { submitted ? 'ping' : '' }"
		>
		{#if !submitted}
			<input
			type="hidden"
			name="_subject"
			value="Syntax Magazine">

			<label for="email">Email:</label>
			<input
				name="_replyto"
				type="email"
				style="display:block"
			/>

			<label for="text">Msg:</label>
			<textarea
				type="text"
				name="text"
				rows="4"
				cols="50"
				style="display:block"
			></textarea>

			<button type="submit">Submit</button>
		{:else}
			<p class="ma0 pb3">{ submitted ? status : '' }</p>
		{/if}
	</form>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
	}

</style>
