<script>
	import AnnualCheck from './components/AnnualCheck.svelte';
	import SelectPlan from './components/SelectPlan.svelte';

	let { formOptions } = $props();

	const handleNext = () => {
		formOptions.step = 3;
	};
	const handleBack = () => {
		formOptions.step = 1;
	};
</script>

<div
	class="z-10 flex flex-col gap-8 px-16 py-8 max-sm:absolute max-sm:top-24 max-sm:mx-4 max-sm:rounded-lg max-sm:bg-white sm:basis-[574px]"
>
	<div class="flex flex-col">
		<h1 class="text-3xl font-bold text-[#02295a]">Select your plan</h1>
		<p class="text-[#9699ab]">You have the option of monthly or yearly billing.</p>
	</div>
	<div class="flex flex-col gap-4 text-[#02295a]">
		<SelectPlan {formOptions} />
		<AnnualCheck {formOptions} />
	</div>
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
