<script lang="ts">
import { cn } from "$lib/utils";
import { Drawer as DrawerPrimitive } from "vaul-svelte";

type $$Props = DrawerPrimitive.DescriptionProps;

export let el: $$Props["el"] = undefined;
let className: $$Props["class"] = undefined;
export { className as class };
</script>

<DrawerPrimitive.Description
	bind:el
	class={cn("text-muted-foreground text-sm", className)}
	{...$$restProps}
>
	<slot />
</DrawerPrimitive.Description>
