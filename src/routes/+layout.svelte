<script lang="ts">
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-gold-nouveau.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';

	import { computePosition, autoUpdate, offset, shift, flip, arrow } from '@floating-ui/dom';
	import { AppShell, AppBar, LightSwitch } from '@skeletonlabs/skeleton';
	import Breadcrumbs from '$lib/components/breadcrumbs.svelte';

	import { storePopup } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, offset, shift, flip, arrow });
</script>

<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<strong class="text-xl">TopTopic</strong>
			</svelte:fragment>
			<div class="ml-4">
				<Breadcrumbs />
			</div>
			<svelte:fragment slot="trail">
				<div class="p4">
					<LightSwitch />
				</div>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<div class="container h-full mx-auto flex justify-center items-center">
		<div class="space-y-8">
			<slot />
		</div>
	</div>
</AppShell>
