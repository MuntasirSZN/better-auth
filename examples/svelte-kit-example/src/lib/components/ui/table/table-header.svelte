<script lang="ts">
import { cn } from "$lib/utils";
import type { HTMLAttributes } from "svelte/elements";

type $$Props = HTMLAttributes<HTMLTableSectionElement>;

let className: $$Props["class"] = undefined;
export { className as class };
</script>

<!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
<thead class={cn("[&_tr]:border-b", className)} {...$$restProps} on:click on:keydown>
	<slot />
</thead>
