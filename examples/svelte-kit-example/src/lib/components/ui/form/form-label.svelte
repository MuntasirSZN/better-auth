<script lang="ts">
import type { Label as LabelPrimitive } from "bits-ui";
import { getFormControl } from "formsnap";
import Label from "../label/label.svelte";
import { cn } from "$lib/utils";

type $$Props = LabelPrimitive.Props;

let className: $$Props["class"] = undefined;
export { className as class };

const { labelAttrs } = getFormControl();
</script>

<Label {...$labelAttrs} class={cn("data-[fs-error]:text-destructive", className)} {...$$restProps}>
	<slot {labelAttrs} />
</Label>
