<script lang="ts">
	import { Dialog as DialogPrimitive } from "bits-ui";
	import { getCtx } from "../ctx.js";

	type $$Props = DialogPrimitive.TriggerProps;

	const {
		refs: { triggerRef },
	} = getCtx();

	export let ref: HTMLButtonElement | null = null;

	$: triggerRef.set(ref ?? undefined);
</script>

<DialogPrimitive.Trigger bind:ref {...$$restProps}>
	{#snippet child({ props })}
		<slot {props} />
	{/snippet}
</DialogPrimitive.Trigger>
