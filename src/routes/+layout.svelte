
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
	import { AppRail, AppRailTile, AppRailAnchor } from '@skeletonlabs/skeleton';
	
	let isFocused: boolean = false;
	let isMobile: boolean = false;

	onMount(() => {
		console.log("Mounted");
		console.log(Device.isMobile);
		isMobile = Device.isMobile;
	});

	let currentTile: number = 0;

</script>

<!-- App Shell -->
<AppShell scrollbarGutter="auto">
	<svelte:fragment slot="header">
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
						<TreeViewItem> Menu 
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

	
	<svelte:fragment slot="sidebarLeft">
		{#if !isMobile}
		<AppRail width="">
				<AppRailAnchor href="/"  title="Account" width="50px">
					<svelte:fragment slot="lead">ICON</svelte:fragment>

				</AppRailAnchor>
			<!-- --- -->
			<AppRailTile bind:group={currentTile} name="tile-1" value={0} title="tile-1">
				<svelte:fragment slot="lead">Services</svelte:fragment>
				<!-- <span>Tile 1</span> -->
			</AppRailTile>
			<AppRailTile bind:group={currentTile} name="tile-2" value={1} title="tile-2">
				<svelte:fragment slot="lead">Products</svelte:fragment>
				<!-- <span>Tile 2</span> -->
			</AppRailTile>
			<AppRailTile bind:group={currentTile} name="tile-3" value={2} title="tile-3">
				<svelte:fragment slot="lead">Technology</svelte:fragment>
				<span>Tile 3</span>
			</AppRailTile>
			<!-- --- -->
			<!-- <svelte:fragment slot="trail">
				<AppRailAnchor href="/" target="_blank" title="Account">(icon)</AppRailAnchor>
			</svelte:fragment> -->
		</AppRail>
		{/if}
	</svelte:fragment>
	

	

	<!-- Page Route Content -->
	<slot />
</AppShell>
