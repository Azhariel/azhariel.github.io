<script lang="ts">
	import '@skeletonlabs/skeleton/themes/theme-gold-nouveau.css'
	import '@skeletonlabs/skeleton/styles/skeleton.css'
	import '../app.postcss'
	import { AppShell, AppBar, type PopupSettings, popup } from '@skeletonlabs/skeleton'
	import { computePosition, autoUpdate, offset, shift, flip, arrow } from '@floating-ui/dom'
	import { storePopup } from '@skeletonlabs/skeleton'
	storePopup.set({ computePosition, autoUpdate, offset, shift, flip, arrow })

	const popupFeatured: PopupSettings = {
		// Represents the type of event that opens/closed the popup
		event: 'click',
		// Matches the data-popup value on your popup element
		target: 'popupFeatured',
		// Defines which side of your trigger the popup will appear
		placement: 'bottom'
	}
</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<strong class="text-xl uppercase">Azhariel</strong>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<button class="btn btn-sm variant-ghost-surface" use:popup={popupFeatured}
					>Curriculum</button
				>

				<div class="card p-4 shadow-xl" data-popup="popupFeatured">
					<a
						class="btn btn-sm variant-ghost-surface"
						href="/CV Renan Z Braga PTBR.pdf"
						target="_blank"
						rel="noreferrer"
					>
						Português
					</a>
					<a
						class="btn btn-sm variant-ghost-surface"
						href="/CV Renan Z Braga ENG.pdf"
						target="_blank"
						rel="noreferrer"
					>
						English
					</a>
				</div>

				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://github.com/azhariel"
					target="_blank"
					rel="noreferrer"
				>
					GitHub
				</a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
