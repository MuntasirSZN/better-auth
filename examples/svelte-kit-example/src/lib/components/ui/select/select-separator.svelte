<script lang="ts">
import { cn } from "$lib/utils";
import { Select as SelectPrimitive } from "bits-ui";

type $$Props = SelectPrimitive.SeparatorProps;

let className: $$Props["class"] = undefined;
export { className as class };
</script>

<SelectPrimitive.Separator class={cn("bg-muted -mx-1 my-1 h-px", className)} {...$$restProps} />
