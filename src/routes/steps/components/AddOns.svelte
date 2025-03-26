<script>
	let { formOptions } = $props();

	const handleOnline = () => {
		formOptions.online = !formOptions.online;
	};
	const handleStorage = () => {
		formOptions.storage = !formOptions.storage;
	};
	const handleProfile = () => {
		formOptions.profile = !formOptions.profile;
	};
</script>

<div class="flex flex-col gap-6">
	<div
		class={`flex items-center gap-6 rounded-lg border p-4 ${formOptions.online ? 'border-[#02295a] bg-[#bfe2fd]' : 'border-[#9699ab]'}`}
	>
		<input
			type="checkbox"
			value=""
			bind:checked={formOptions.online}
			class="h-5 w-5 rounded-sm border-gray-300 accent-[#473dff]"
		/>
		<div class="flex flex-col">
			<p class="font-medium text-[#02295a]">Online service</p>
			<p class="text-sm text-[#9699ab]">Access to multiplayer games</p>
		</div>
		<p class="ml-auto text-sm text-[#473dff]">{formOptions.annual ? '+$10/yr' : '+$1/mo'}</p>
	</div>
	<div
		class={`flex items-center gap-6 rounded-lg border p-4 ${formOptions.storage ? 'border-[#02295a] bg-[#bfe2fd]' : 'border-[#9699ab]'}`}
	>
		<input
			type="checkbox"
			value=""
			bind:checked={formOptions.storage}
			class="h-5 w-5 rounded-sm border-gray-300 accent-[#473dff]"
		/>
		<div class="flex flex-col">
			<p class="font-medium text-[#02295a]">Larger storage</p>
			<p class="text-sm text-[#9699ab]">Extra 1TB of cloud save</p>
		</div>
		<p class="ml-auto text-sm text-[#473dff]">{formOptions.annual ? '+$20/yr' : '+$2/mo'}</p>
	</div>
	<div
		class={`flex items-center gap-6 rounded-lg border p-4 ${formOptions.profile ? 'border-[#02295a] bg-[#bfe2fd]' : 'border-[#9699ab]'}`}
	>
		<input
			type="checkbox"
			value=""
			bind:checked={formOptions.profile}
			class="h-5 w-5 rounded-sm border-gray-300 accent-[#473dff]"
		/>
		<div class="flex flex-col">
			<p class="font-medium text-[#02295a]">Customizable profile</p>
			<p class="text-sm text-[#9699ab]">Custom themes on your profile</p>
		</div>
		<p class="ml-auto text-sm text-[#473dff]">{formOptions.annual ? '+$20/yr' : '+$2/mo'}</p>
	</div>
</div>
