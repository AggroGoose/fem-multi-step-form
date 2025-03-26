<script>
	let { formOptions } = $props();

	let onlinePrice = $derived(formOptions.online ? 1 : 0);
	let profilePrice = $derived(formOptions.profile ? 2 : 0);
	let storagePrice = $derived(formOptions.storage ? 2 : 0);
	let annualMultiplier = $derived(formOptions.annual ? 10 : 1);
	let totalPrice = $derived(
		(formOptions.planPrice + onlinePrice + storagePrice + profilePrice) * annualMultiplier
	);

	const handleNext = () => {
		formOptions.step = 4;
	};
	const handleBack = () => {
		formOptions.step = 3;
	};
	const handleChange = () => {
		formOptions.step = 2;
	};
</script>

<div class="flex basis-[574px] flex-col gap-8 px-16 py-8">
	<div class="flex flex-col">
		<h1 class="text-3xl font-bold text-[#02295a]">Finishing up</h1>
		<p class="text-[#9699ab]">Double-check everything looks OK before confirming.</p>
	</div>
	<div class="flex flex-col rounded-lg bg-[#f0f6ff]">
		<div class="flex justify-between p-4">
			<div class="flex flex-col items-start">
				<p class="font-bold text-[#02295a]">
					{formOptions.plan === 1 ? 'Arcade' : formOptions.plan === 2 ? 'Advanced' : 'Pro'} ({formOptions.annual
						? 'Yearly'
						: 'Monthly'})
				</p>
				<button
					onclick={handleChange}
					class="cursor-pointer text-sm text-[#9699ab] underline hover:text-[#02295a]"
					>Change</button
				>
			</div>
			<p class="font-bold text-[#02295a]">
				${formOptions.annual ? formOptions.planPrice * 10 + '/yr' : formOptions.planPrice + '/mo'}
			</p>
		</div>
		<hr class="w-5/6 self-center text-[#d6d9e6]" />
		<div class="flex flex-col gap-4 p-4">
			{#if formOptions.online}
				<div class="flex justify-between text-sm">
					<p class="text-[#9699ab]">Online service</p>
					<p class="text-[#02295a]">{formOptions.annual ? '+$10/yr' : '+$1/mo'}</p>
				</div>
			{/if}
			{#if formOptions.storage}
				<div class="flex justify-between text-sm">
					<p class="text-[#9699ab]">Larger storage</p>
					<p class="text-[#02295a]">{formOptions.annual ? '+$20/yr' : '+$2/mo'}</p>
				</div>
			{/if}
			{#if formOptions.profile}
				<div class="flex justify-between text-sm">
					<p class="text-[#9699ab]">Customizable profile</p>
					<p class="text-[#02295a]">{formOptions.annual ? '+$20/yr' : '+$2/mo'}</p>
				</div>
			{/if}
		</div>
	</div>
	<div class="flex justify-between px-4">
		<p class="text-sm text-[#9699ab]">Total(per {formOptions.annual ? 'year' : 'month'})</p>
		<p class="text-lg font-bold text-[#473dff]">${totalPrice}/{formOptions.annual ? 'yr' : 'mo'}</p>
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
