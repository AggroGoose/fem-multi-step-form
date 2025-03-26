<script>
	let { formOptions } = $props();

	const handleNext = () => {
		formOptions.step = 4;
	};
	const handleBack = () => {
		formOptions.step = 2;
	};
</script>

<div class="flex basis-[574px] flex-col gap-8 px-16 py-8">
	<div class="flex flex-col">
		<h1 class="text-3xl font-bold text-[#02295a]">Pick add-ons</h1>
		<p class="text-[#9699ab]">Add-ons help enhance your gaming experience.</p>
	</div>
	<div class="flex flex-col gap-4 text-[#02295a]">We made it to step three, gooby!</div>
	<div class="mt-auto flex items-center justify-between">
		<button
			onclick={handleBack}
			class="cursor-pointer font-medium text-[#9699ab] hover:text-[#02295a]">Go Back</button
		>
		<button
			onclick={handleNext}
			class="cursor-pointer rounded-lg bg-[#02295a] px-6 py-3 text-white hover:bg-[#473dff]"
			>Next Step</button
		>
	</div>
</div>
