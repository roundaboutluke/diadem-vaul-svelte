<script lang="ts">
	import { Dialog as DialogPrimitive } from "bits-ui";
	import { getCtx } from "../ctx.js";

	type $$Props = DialogPrimitive.TriggerProps;

	const {
		refs: { triggerRef },
	} = getCtx();

	export let ref: $$Props["ref"] = undefined;

	$: triggerRef.set((ref as HTMLButtonElement | null) ?? undefined);
</script>

<DialogPrimitive.Trigger bind:ref {...$$restProps}>
	{#snippet child({ props })}
		<slot {props} />
	{/snippet}
</DialogPrimitive.Trigger>
