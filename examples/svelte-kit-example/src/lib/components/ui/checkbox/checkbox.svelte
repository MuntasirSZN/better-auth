<script lang="ts">
import { cn } from "$lib/utils";
import { Checkbox as CheckboxPrimitive } from "bits-ui";
import Minus from "svelte-radix/Minus.svelte";
import Check from "svelte-radix/Check.svelte";

type $$Props = CheckboxPrimitive.Props & {
	class?: string | null | undefined;
};
type $$Events = CheckboxPrimitive.Events;

let className: $$Props["class"] = undefined;
export let checked: $$Props["checked"] = false;
export { className as class };
</script>

<CheckboxPrimitive.Root
	class={cn(
		"border-primary focus-visible:ring-ring data-[state=checked]:bg-primary data-[state=checked]:text-primary-foreground peer box-content h-4 w-4 shrink-0 rounded-sm border shadow focus-visible:outline-none focus-visible:ring-1 disabled:cursor-not-allowed disabled:opacity-50 data-[disabled=true]:cursor-not-allowed data-[disabled=true]:opacity-50",
		className as string
	)}
	bind:checked
	on:click
	{...$$restProps}
>
	<CheckboxPrimitive.Indicator
		class={cn("flex h-4 w-4 items-center justify-center text-current")}
		let:isChecked
		let:isIndeterminate
	>
		{#if isIndeterminate}
			<Minus class="h-3.5 w-3.5" />
		{:else}
			<Check class={cn("h-3.5 w-3.5", !isChecked && "text-transparent")} />
		{/if}
	</CheckboxPrimitive.Indicator>
</CheckboxPrimitive.Root>
