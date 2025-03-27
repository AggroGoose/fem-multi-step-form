<script>
	import Sidebar from './components/Sidebar.svelte';
	import StepFour from './steps/StepFour.svelte';
	import StepOne from './steps/StepOne.svelte';
	import StepThree from './steps/StepThree.svelte';
	import StepTwo from './steps/StepTwo.svelte';

	let formOptions = $state({
		step: 1,
		name: '',
		email: '',
		phone: '',
		plan: 1,
		planPrice: 9,
		annual: false,
		online: false,
		storage: false,
		profile: false
	});

	let currentStep = $derived(formOptions.step);
</script>

<main class="min-h-screen bg-[#f0f6ff] font-sans sm:flex sm:items-center">
	<div
		class="m-auto flex rounded-2xl shadow-md max-sm:flex-col sm:min-w-[880px] sm:bg-white sm:p-4"
	>
		<Sidebar {currentStep} />
		{#if currentStep === 1}
			<StepOne {formOptions} />
		{:else if currentStep === 2}
			<StepTwo {formOptions} />
		{:else if currentStep === 3}
			<StepThree {formOptions} />
		{:else if currentStep === 4}
			<StepFour {formOptions} />
		{/if}
	</div>
</main>
