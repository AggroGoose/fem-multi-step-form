<script>
	import AddOns from './components/AddOns.svelte';

	let { formOptions } = $props();

	const handleNext = () => {
		formOptions.step = 4;
	};
	const handleBack = () => {
		formOptions.step = 2;
	};
</script>

<div
	class="z-10 flex flex-col gap-8 px-16 py-8 max-sm:absolute max-sm:top-24 max-sm:mx-4 max-sm:rounded-lg max-sm:bg-white sm:basis-[574px]"
>
	<div
		class="m-auto flex w-full flex-col items-center gap-8 self-center justify-self-center text-center"
	>
		<img class="w-20" src="/images/icon-thank-you.svg" alt="green checkmark" />
		<h1 class="text-3xl font-bold text-[#02295a]">Thank you!</h1>
		<p class="max-w-[370px] text-[#9699ab]">
			Thanks for confirming your subscription! We hope you have fun using our platform. If you ever
			need support, please feel free to email us at support@loremgaming.com.
		</p>
	</div>
</div>
