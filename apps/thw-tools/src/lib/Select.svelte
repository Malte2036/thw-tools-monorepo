<script lang="ts">
	interface Props {
		options: { value: string; label: string }[];
		selected: string;
		label?: string | undefined;
	}

	let { options, selected = $bindable(), label = undefined }: Props = $props();
</script>

<div class="flex flex-col gap-1">
	{#if label !== undefined}
		<label class="font-bold" for="selectField">{label}</label>
	{/if}
	<select bind:value={selected} class="border border-black rounded-lg py-1 px-2" id="selectField">
		{#each options as option (option)}
			<option value={option.value}>{option.label}</option>
		{/each}
	</select>
</div>
