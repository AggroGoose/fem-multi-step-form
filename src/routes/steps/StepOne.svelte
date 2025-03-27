<script>
	let { formOptions } = $props();

	let nameError = $state(false);
	let emailError = $state(false);
	let phoneError = $state(false);

	const handleNext = () => {
		if (formOptions.name.length < 1) {
			nameError = true;
			return;
		}
		nameError = false;
		if (formOptions.email.length < 1) {
			emailError = true;
			return;
		}
		emailError = false;
		if (formOptions.phone.length < 1) {
			phoneError = true;
			return;
		}
		phoneError = false;
		formOptions.step = 2;
	};
</script>

<div
	class="z-10 flex flex-col gap-8 px-16 py-8 max-sm:absolute max-sm:top-24 max-sm:mx-4 max-sm:rounded-lg max-sm:bg-white sm:basis-[574px]"
>
	<div class="flex flex-col">
		<h1 class="text-3xl font-bold text-[#02295a]">Personal info</h1>
		<p class="text-[#9699ab]">Please provide your name, email address, and phone number.</p>
	</div>
	<div class="flex w-full flex-col gap-4 text-[#02295a]">
		<label class="block">
			<div class="flex justify-between text-[#02295a]">
				<p>Name</p>
				{#if nameError}
					<p class="font-medium text-[#ed3548]">This field is required</p>
				{/if}
			</div>
			<input
				type="text"
				class={`mt-1 block w-full rounded-lg font-medium ${nameError ? 'border-[#ed3548]' : 'border-[#9699ab]'}`}
				bind:value={formOptions.name}
			/>
		</label>
		<label class="block">
			<div class="flex justify-between text-[#02295a]">
				<p>Email Address</p>
				{#if emailError}
					<p class="font-medium text-[#ed3548]">This field is required</p>
				{/if}
			</div>
			<input
				type="email"
				class={`mt-1 block w-full rounded-lg font-medium ${emailError ? 'border-[#ed3548]' : 'border-[#9699ab]'}`}
				placeholder="john@example.com"
				bind:value={formOptions.email}
			/>
		</label>
		<label class="block">
			<div class="flex justify-between text-[#02295a]">
				<p>Phone Number</p>
				{#if phoneError}
					<p class="font-medium text-[#ed3548]">This field is required</p>
				{/if}
			</div>
			<input
				type="text"
				class={`mt-1 block w-full rounded-lg font-medium ${phoneError ? 'border-[#ed3548]' : 'border-[#9699ab]'}`}
				placeholder="e.g. +1 234 567 890"
				bind:value={formOptions.phone}
			/>
		</label>
	</div>
	<button
		onclick={handleNext}
		class="mt-auto ml-auto cursor-pointer rounded-lg bg-[#02295a] px-6 py-3 text-white hover:bg-[#473dff]"
		>Next Step</button
	>
</div>
