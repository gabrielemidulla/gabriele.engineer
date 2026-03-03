<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
	
	let sidebarOpen = $state(false);

	const links = [
		{ href: '/about-me', text: 'about me' },
		{ href: '/blog', text: 'blog' },
		{ href: '/contact-me', text: 'contact me' }
	];
</script>

<div class="w-screen">
	<div class="w-full max-w-4xl mx-auto flex items-center">
		<a href="/" class="stable-link" data-text="gabriele.engineer">gabriele.engineer</a>

		<div class="ml-auto hidden sm:flex">
			{#each links as link}
				<a href={link.href} class="stable-link" data-text={link.text}>
					{link.text}
				</a>
			{/each}
		</div>
		<button class="sm:hidden ml-auto mr-6" onclick={() => sidebarOpen = true}>
			<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
				<path d="M3 12h18"></path>
				<path d="M3 6h18"></path>
				<path d="M3 18h18"></path>
			</svg>
		</button>
	</div>
</div>

<div class={`fixed top-0 left-0 w-full h-full bg-white z-50 transform ${sidebarOpen ? 'translate-x-0' : '-translate-x-full'} transition-transform duration-300 ease-in-out`}>
	<div class="absolute top-4 right-4" onclick={() => sidebarOpen = false}>
		<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
			<line x1="18" y1="6" x2="6" y2="18"></line>
			<line x1="6" y1="6" x2="18" y2="18"></line>
		</svg>
	</div>
	<div class="w-full h-full flex flex-col items-center justify-center gap-8">
		{#each links as link}
			<a href={link.href} class="text-2xl font-bold" onclick={() => sidebarOpen = false}>
				{link.text}
			</a>
		{/each}
	</div>
</div>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>
{@render children()}

<style>
	.stable-link {
		padding: 1rem;
		display: inline-flex;
		flex-direction: column;
		align-items: center;
		text-decoration: none;
		color: #333;
	}

	.stable-link::after {
		content: attr(data-text);
		font-weight: bold;
		height: 0;
		visibility: hidden;
		overflow: hidden;
	}

	.stable-link:hover {
		font-weight: bold;
	}
</style>