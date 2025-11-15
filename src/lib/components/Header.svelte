<script>
	import * as Sheet from '$lib/components/ui/sheet/index.js';
	import { Button } from '$lib/components/ui/button/index.js';
	import { Menu } from 'lucide-svelte';

	const navLinks = [
		{ href: '/', label: 'Home' },
		{ href: '/about', label: 'About & Menu' },
		{ href: '/contact', label: 'Contact' }
	];
</script>

<header
	class="sticky top-0 z-50 w-full border-b border-border/40 bg-background/95 backdrop-blur supports-[backdrop-filter]:bg-background/60"
>
	<div class="container mx-auto flex h-16 max-w-7xl items-center justify-between px-4">
		<a href="/" class="flex items-center space-x-2">
			<h1 class="font-display text-2xl font-bold text-primary">Café Ribeira</h1>
		</a>

		<nav class="hidden items-center space-x-6 md:flex">
			{#each navLinks as link}
				<a
					href={link.href}
					class="font-body text-sm font-medium text-foreground/80 transition-colors hover:text-primary"
				>
					{link.label}
				</a>
			{/each}
		</nav>

		<Sheet.Root>
			<Sheet.Trigger asChild class="md:hidden">
				<Button variant="ghost" size="icon" class="" disabled={false}>
					<Menu class="h-5 w-5" />
					<span class="sr-only">Toggle menu</span>
				</Button>
			</Sheet.Trigger>
			<Sheet.Content side="right" class="w-[300px] sm:w-[400px]" portalProps={{}}>
				<nav class="mt-8 flex flex-col space-y-4 px-4">
					{#each navLinks as link}
						<a
							href={link.href}
							class="font-body text-lg font-medium text-foreground/80 transition-colors hover:text-primary"
						>
							{link.label}
						</a>
					{/each}
				</nav>
			</Sheet.Content>
		</Sheet.Root>
	</div>
</header>
