<script>
	let { currentStep } = $props();
</script>

<div class="relative sm:basis-[274px]">
	<img class="hidden sm:block" src="/images/bg-sidebar-desktop.svg" alt="background for sidebar" />
	<img
		class="w-screen sm:hidden"
		src="/images/bg-sidebar-mobile.svg"
		alt="background for sidebar"
	/>
	<ul
		class="absolute top-8 left-1/2 flex gap-4 max-sm:-translate-x-1/2 sm:left-8 sm:flex-col sm:gap-8"
	>
		<li class="flex items-center gap-4">
			<button
				class={`min-w-[2em] rounded-full  p-1 font-medium  ${currentStep === 1 ? 'bg-[#bfe2fd]' : 'border border-white text-white'}`}
				>1</button
			>
			<div class="flex flex-col text-sm leading-tight text-white max-sm:hidden">
				<p>STEP 1</p>
				<p class="font-bold">YOUR INFO</p>
			</div>
		</li>
		<li class="flex items-center gap-4">
			<button
				class={`min-w-[2em] rounded-full  p-1 font-medium  ${currentStep === 2 ? 'bg-[#bfe2fd]' : 'border border-white text-white'}`}
				>2</button
			>
			<div class="flex flex-col text-sm leading-tight text-white max-sm:hidden">
				<p>STEP 2</p>
				<p class="font-bold">SELECT PLAN</p>
			</div>
		</li>
		<li class="flex items-center gap-4">
			<button
				class={`min-w-[2em] rounded-full  p-1 font-medium  ${currentStep === 3 ? 'bg-[#bfe2fd]' : 'border border-white text-white'}`}
				>3</button
			>
			<div class="flex flex-col text-sm leading-tight text-white max-sm:hidden">
				<p>STEP 3</p>
				<p class="font-bold">ADD-ONS</p>
			</div>
		</li>
		<li class="flex items-center gap-4">
			<button
				class={`min-w-[2em] rounded-full  p-1 font-medium  ${currentStep === 4 ? 'bg-[#bfe2fd]' : 'border border-white text-white'}`}
				>4</button
			>
			<div class="flex flex-col text-sm leading-tight text-white max-sm:hidden">
				<p>STEP 4</p>
				<p class="font-bold">SUMMARY</p>
			</div>
		</li>
	</ul>
</div>
