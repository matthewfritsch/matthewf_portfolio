<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';

	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import { LightSwitch, autoModeWatcher } from '@skeletonlabs/skeleton';
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
</script>

<!-- App Shell -->
<svelte:head>{@html `<script>${autoModeWatcher.toString()} autoModeWatcher();</script>`}</svelte:head>
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar background='bg-transparent' border='border-b-2 border-black dark:border-white'>
			<svelte:fragment slot="lead">
				<LightSwitch/>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://www.linkedin.com/in/matthew-fritsch-9ba95b195/"
					target="_blank"
					rel="noreferrer"
				>
					LinkedIn
				</a>
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://github.com/matthewfritsch"
					target="_blank"
					rel="noreferrer"
				>
					GitHub
				</a>
				<a
					class="btn btn-sm variant-ghost-surface"
					href="mailto:contact@matthewfritsch.com"
					target="_blank"
					rel="noreferrer"
				>
					Email
				</a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
