<script>
	let { formOptions } = $props();

	const handleNext = () => {
		formOptions.step = 2;
	};
</script>

<div class="flex basis-[574px] flex-col gap-8 px-16 py-8">
	<div class="flex flex-col">
		<h1 class="text-3xl font-bold text-[#02295a]">Personal info</h1>
		<p class="text-[#9699ab]">Please provide your name, email address, and phone number.</p>
	</div>
	<div class="flex w-full flex-col gap-4 text-[#02295a]">
		<label class="block">
			<span class="text-[#02295a]"> Name </span>
			<input
				type="text"
				class="mt-1 block w-full rounded-lg font-medium"
				bind:value={formOptions.name}
			/>
		</label>
		<label class="block">
			<span class="text-[#02295a]"> Email Address </span>
			<input
				type="email"
				class="mt-1 block w-full rounded-lg font-medium"
				placeholder="john@example.com"
				bind:value={formOptions.email}
			/>
		</label>
		<label class="block">
			<span class="text-[#02295a]"> Phone Number </span>
			<input
				type="text"
				class="mt-1 block w-full rounded-lg font-medium"
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
