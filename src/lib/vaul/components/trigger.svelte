<script lang="ts">
	import { Dialog as DialogPrimitive } from "bits-ui";
	import TriggerWrapper from "./trigger-wrapper.svelte";
	import { getCtx } from "../ctx.js";

	type $$Props = DialogPrimitive.TriggerProps;
	type $$Events = DialogPrimitive.TriggerEvents;

	const {
		refs: { triggerRef },
	} = getCtx();

	export let ref: HTMLButtonElement | null = null;
	export let asChild: boolean = false;

	$: triggerRef.set(ref ?? undefined);
</script>

{#if asChild}
	<DialogPrimitive.Trigger {asChild} let:builder on:click on:keydown bind:ref {...$$restProps}>
		<TriggerWrapper meltBuilder={builder} let:newBuilder>
			<slot builder={newBuilder} />
		</TriggerWrapper>
	</DialogPrimitive.Trigger>
{:else}
	<DialogPrimitive.Trigger let:builder on:click on:keydown bind:ref {...$$restProps}>
		<slot {builder} />
	</DialogPrimitive.Trigger>
{/if}
