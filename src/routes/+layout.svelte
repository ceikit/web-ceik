
<script lang="ts">
	import "../app.postcss";
	import { onMount } from 'svelte';
	import {
		AppShell,
		AppBar,
		TreeView,
		TreeViewItem,
	} from "@skeletonlabs/skeleton";	

	// import svelte-device-info

	// Floating UI for Popups
	import {
		computePosition,
		autoUpdate,
		flip,
		shift,
		offset,
		arrow,
	} from "@floating-ui/dom";
	import { storePopup } from "@skeletonlabs/skeleton";
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });
	import Device from "svelte-device-info";
	
	let isFocused: boolean = false;
	let isMobile: boolean = false;

	onMount(() => {
		console.log("Mounted");
		console.log(Device.isMobile);
		isMobile = Device.isMobile;
	});

</script>

<!-- App Shell -->
<AppShell scrollbarGutter="auto">
	<svelte:fragment slot="pageHeader">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<a href="/">
					<strong class="text-xl uppercase">Radon Tech</strong>
				</a>
			</svelte:fragment>
		
			<svelte:fragment slot="trail">
				{#if isMobile}
					<TreeView>
						<TreeViewItem class="btn btn-sm variant-ghost-surface"> Menu 
							<svelte:fragment slot="children">
								<TreeViewItem > 
									<a class="btn btn-sm variant-ghost-surface" href="/about">About</a>
								</TreeViewItem>
								<TreeViewItem > 
									<a class="btn btn-sm variant-ghost-surface" href="/services">Services</a>
								</TreeViewItem>
								<TreeViewItem > 
									<a class="btn btn-sm variant-ghost-surface" href="/products">Products</a>
								</TreeViewItem>
								<TreeViewItem > 
									<a class="btn btn-sm variant-ghost-surface" href="/contacts">Contacts</a>
								</TreeViewItem>
							</svelte:fragment>
						</TreeViewItem>
					</TreeView>
				{/if}

				{#if !isMobile}
					<a class="btn btn-sm variant-ghost-surface" href="/about">About</a>
					<a class="btn btn-sm variant-ghost-surface" href="/services">Services</a>
					<a class="btn btn-sm variant-ghost-surface" href="/products">Products</a>
					<a class="btn btn-sm variant-ghost-surface" href="/contact">Contact</a>
				{/if}
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
