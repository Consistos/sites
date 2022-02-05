<script>
	import '@sveltejs/site-kit/base.css';
	import { setContext } from 'svelte';
	import { page, navigating, session } from '$app/stores';
	import { Icon, Icons, Nav, NavItem, SkipLink } from '@sveltejs/site-kit';
	import PreloadingIndicator from '$lib/components/PreloadingIndicator.svelte';

	setContext('app', {
		login: () => {
			const login_window = window.open(
				`${window.location.origin}/auth/login`,
				'login',
				'width=600,height=400'
			);

			window.addEventListener('message', function handler(event) {
				login_window.close();
				window.removeEventListener('message', handler);
				$session.user = event.data.user;
			});
		},

		logout: async () => {
			const r = await fetch(`/auth/logout`, {
				credentials: 'include'
			});

			if (r.ok) $session.user = null;
		}
	});
</script>

<Icons />

{#if $navigating && $navigating.to}
	<PreloadingIndicator />
{/if}

{#if $page.url.pathname !== '/repl/embed'}
	<SkipLink href="#main" />
	<Nav {page} logo="/wexpo.svg">
		<svelte:fragment slot="nav-center">
			<NavItem href="#Offre">Offre</NavItem>
			<NavItem href="#Comparaison">Comparaison</NavItem>
			<NavItem href="#Tarifs">Tarifs</NavItem>
			<NavItem href="/blog">Blog</NavItem>
		</svelte:fragment>

		<svelte:fragment slot="nav-right">
			<NavItem external="https://twitter.com/wexpo">Twitter</NavItem>
		</svelte:fragment>
	</Nav>
{/if}

<main id="main">
	<slot />
</main>

<style>
	main {
		position: relative;
		margin-inline: auto;
		margin-block: 0;
		/* padding-inline: var(--side-nav);
		padding-block: var(--nav-h) 0; */
		padding-block-start: var(--nav-h);
	}

	.small {
		display: inline;
	}

	.large {
		display: none;
	}

	@media (min-width: 800px) {
		.small {
			display: none;
		}

		.large {
			display: inline;
		}
	}
</style>
