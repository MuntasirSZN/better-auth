<script lang="ts">
import { cn } from "$lib/utils";
import { Calendar as CalendarPrimitive } from "bits-ui";

type $$Props = CalendarPrimitive.CellProps;

export let date: $$Props["date"];
let className: $$Props["class"] = undefined;
export { className as class };
</script>

<CalendarPrimitive.Cell
	{date}
	class={cn(
		"[&:has([data-selected])]:bg-accent [&:has([data-selected][data-outside-month])]:bg-accent/50 relative p-0 text-center text-sm focus-within:relative focus-within:z-20 [&:has([data-selected])]:rounded-md",
		className
	)}
	{...$$restProps}
>
	<slot />
</CalendarPrimitive.Cell>
