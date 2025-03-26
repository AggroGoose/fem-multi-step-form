<script>
	let { formOptions } = $props();
</script>

<label class="mt-8 inline-flex cursor-pointer items-center gap-3 self-center">
	<span class={`font-medium ${!formOptions.annual ? 'text-[#02295a]' : 'text-[#9699ab]'}`}
		>Monthly</span
	>
	<input type="checkbox" value="" bind:checked={formOptions.annual} class="peer sr-only" />
	<div
		class="peer relative h-4 w-8 rounded-full bg-[#02295a] after:absolute after:start-[4px] after:top-[2px] after:h-3 after:w-3 after:rounded-full after:bg-white after:transition-all after:content-[''] peer-checked:after:translate-x-full peer-checked:after:border-white rtl:peer-checked:after:-translate-x-full"
	></div>
	<span class={`font-medium ${formOptions.annual ? 'text-[#02295a]' : 'text-[#9699ab]'}`}
		>Yearly</span
	>
</label>
