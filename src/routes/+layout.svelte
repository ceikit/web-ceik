
<script lang="ts">
	import "../app.postcss";
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

	

	// if page is rendered change isFocused to true
	$: if (isFocused) {
		storePopup.update((state) => ({ ...state, isFocused }));
	}

	if (isFocused) {
		console.log("ASDADA" + Device.isMobile)
	} else {
		console.log("isNotFocused");
	}

	// if page is not rendered change isFocused to false
	$: if (!isFocused) {
		storePopup.update((state) => ({ ...state, isFocused }));
	}

	if (isFocused) {
		console.log("isFocused")}

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

			

				<div> GGG</div>
				
				<a class="btn btn-sm variant-ghost-surface" href="/about"
					>About</a
				>
				<a class="btn btn-sm variant-ghost-surface" href="/services"
					>Services</a
				>
				<a class="btn btn-sm variant-ghost-surface" href="/products"
					>Products</a
				>
				<TreeView>
					<TreeViewItem>
						(item 1)
						<svelte:fragment slot="children">
							<TreeViewItem>
								(Child 1)
								<svelte:fragment slot="children">
									<TreeViewItem>
										(Child of Child 1)
									</TreeViewItem>
									<TreeViewItem>
										(Child of Child 2)
									</TreeViewItem>
								</svelte:fragment>
							</TreeViewItem>
							<TreeViewItem>(Child 2)</TreeViewItem>
						</svelte:fragment>
					</TreeViewItem>
					<TreeViewItem>(item 2)</TreeViewItem>
				</TreeView>

				<a class="btn btn-sm variant-ghost-surface" href="/contact"
					>Contact</a
				>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
