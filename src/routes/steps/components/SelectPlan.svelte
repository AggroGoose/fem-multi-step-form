<script>
	let { formOptions } = $props();

	const handleArcade = () => {
		formOptions.plan = 1;
		formOptions.planPrice = 9;
	};
	const handleAdvanced = () => {
		formOptions.plan = 2;
		formOptions.planPrice = 12;
	};
	const handlePro = () => {
		formOptions.plan = 3;
		formOptions.planPrice = 15;
	};
</script>

<div class="flex gap-6 max-sm:flex-col">
	<button
		onclick={handleArcade}
		class={`flex cursor-pointer gap-4 rounded-lg border p-4 sm:basis-1/3 sm:flex-col sm:items-start sm:gap-8 ${formOptions.plan === 1 ? 'border-[#02295a] bg-[#bfe2fd]' : 'border-[#9699ab]'}`}
	>
		<img src="/images/icon-arcade.svg" alt="joystick icon" />
		<div class="flex flex-col items-start">
			<p class="font-medium text-[#02295a]">Arcade</p>
			<p class="text-sm text-[#9699ab]">{formOptions.annual ? '$90/yr' : '$9/mo'}</p>
			{#if formOptions.annual}
				<p class="mt-1 text-xs text-[#02295a]">2 months free</p>
			{/if}
		</div>
	</button>
	<button
		onclick={handleAdvanced}
		class={`flex cursor-pointer gap-4 rounded-lg border p-4 sm:basis-1/3 sm:flex-col sm:items-start sm:gap-8 ${formOptions.plan === 2 ? 'border-[#02295a] bg-[#bfe2fd]' : 'border-[#9699ab]'}`}
	>
		<img src="/images/icon-advanced.svg" alt="controller icon" />
		<div class="flex flex-col items-start">
			<p class="font-medium text-[#02295a]">Advanced</p>
			<p class="text-sm text-[#9699ab]">{formOptions.annual ? '$120/yr' : '$12/mo'}</p>
			{#if formOptions.annual}
				<p class="mt-1 text-xs text-[#02295a]">2 months free</p>
			{/if}
		</div>
	</button>
	<button
		onclick={handlePro}
		class={`flex cursor-pointer gap-4 rounded-lg border p-4 sm:basis-1/3 sm:flex-col sm:items-start sm:gap-8 ${formOptions.plan === 3 ? 'border-[#02295a] bg-[#bfe2fd]' : 'border-[#9699ab]'}`}
	>
		<img src="/images/icon-pro.svg" alt="joystick icon" />
		<div class="flex flex-col items-start">
			<p class="font-medium text-[#02295a]">Pro</p>
			<p class="text-sm text-[#9699ab]">{formOptions.annual ? '$150/yr' : '$15/mo'}</p>
			{#if formOptions.annual}
				<p class="mt-1 text-xs text-[#02295a]">2 months free</p>
			{/if}
		</div>
	</button>
</div>
