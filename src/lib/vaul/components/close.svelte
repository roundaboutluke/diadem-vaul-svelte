<script lang="ts">
	import { Dialog as DialogPrimitive } from "bits-ui";
	import type { CloseProps } from "./types.js";

	type $$Props = CloseProps;

	export let ref: $$Props["ref"] = undefined;
</script>

<DialogPrimitive.Close bind:ref {...$$restProps}>
	{#snippet child({ props })}
		<slot {props} />
	{/snippet}
</DialogPrimitive.Close>
