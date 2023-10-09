<script lang="ts">
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });
	let isFocused: boolean = true;

</script>


<!-- App Shell -->
<AppShell scrollbarGutter="auto">
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<strong class="text-xl uppercase">Radon Tech</strong>
			</svelte:fragment>
			<!-- <svelte:fragment slot="trail">
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://discord.gg/EXqV7W8MtY"
					target="_blank"
					rel="noreferrer"
				>
					Discord
				</a>
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://twitter.com/SkeletonUI"
					target="_blank"
					rel="noreferrer"
				>
					Twitter
				</a>
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://github.com/skeletonlabs/skeleton"
					target="_blank"
					rel="noreferrer"
				>
					GitHub
				</a>
			</svelte:fragment> -->
			<svelte:fragment slot="trail">
				<!-- Adjust, add or remove these links as needed -->
				<a class="btn btn-sm variant-ghost-surface" href="#about">About</a>
				<a class="btn btn-sm variant-ghost-surface" href="#services">Services</a>
				<a class="btn btn-sm variant-ghost-surface" href="#products">Products</a>
				<a class="btn btn-sm variant-ghost-surface" href="#contact">Contact</a>
			</svelte:fragment>
		</AppBar>
		<script>
			import { focusTrap } from '@sveltejs/site-kit';
			import { onMount } from 'svelte';

			let isFocused = true;

			onMount(() => {
				const trap = focusTrap(document.querySelector('form'));
				trap.activate();
				return () => {
					trap.deactivate();
				};
			});
		</script>

		<form>
			<input type="text" placeholder="Name" />
			<button class="btn variant-filled-primary">Submit</button>
		</form>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
