<script>
	let name = '';
	let email = '';
	let message = '';
	let isSubmitting = false;
	let successMessage = '';

	const submitForm = async () => {
		isSubmitting = true;

		//logic here

		setTimeout(() => {
			successMessage = 'meowmeowmeow';
			isSubmitting = false;
		}, 1000);
	};
</script>

<div class="flex justify-center items-center min-h-screen">
	<div class="max-w-md w-full p-6">
		<h1 class="text-2xl font-bold mb-4">Contact Us</h1>
		<form on:submit|preventDefault={submitForm}>
			<div class="mb-4">
				<label for="name" class="block text-sm font-medium">Your Name</label>
				<input
					id="name"
					type="text"
					bind:value={name}
					class="w-full px-3 py-2 rounded-md"
					placeholder="Enter your name"
					required
				/>
			</div>

			<div class="mb-4">
				<label for="email" class="block text-sm font-medium">Your Email</label>
				<input
					id="email"
					type="email"
					bind:value={email}
					class="w-full px-3 py-2 rounded-md"
					placeholder="Enter your email"
					required
				/>
			</div>

			<div class="mb-4">
				<label for="message" class="block text-sm font-medium">Your Message</label>
				<textarea
					id="message"
					bind:value={message}
					class="w-full px-3 py-2 rounded-md"
					placeholder="Enter your message"
					rows="4"
					required
				></textarea>
			</div>

			{#if successMessage}
				<div class="mb-4">{successMessage}</div>
			{/if}

			<div class="mb-4">
				<button type="submit" class="w-full button px-4 py-2 rounded-md" disabled={isSubmitting}>
					{#if isSubmitting}
						Submitting...
					{:else}
						Submit
					{/if}
				</button>
			</div>
		</form>
	</div>
</div>
