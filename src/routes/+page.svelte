<script>
	import { Button } from '$lib/components/ui/button/index.js';
	import * as Card from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Phone, MapPin, Clock, Coffee, Croissant, UtensilsCrossed } from 'lucide-svelte';
	import { Root } from '$lib/components/ui/sheet';

	const menuHighlights = [
		{
			name: 'Pastel de Nata',
			description: 'Traditional Portuguese custard tart',
			price: '€1.50',
			icon: Coffee
		},
		{
			name: 'Bola de Berlim',
			description: 'Fresh cream-filled doughnut',
			price: '€1.80',
			icon: Croissant
		},
		{
			name: 'Francesinha',
			description: "Porto's famous sandwich",
			price: '€9.50',
			icon: UtensilsCrossed
		}
	];

	const galleryImages = [
		'https://images.unsplash.com/photo-1509042239860-f550ce710b93?w=600&h=600&fit=crop',
		'https://images.unsplash.com/photo-1514432324607-a09d9b4aefdd?w=600&h=600&fit=crop',
		'https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?w=600&h=600&fit=crop',
		'https://images.unsplash.com/photo-1511920170033-f8396924c348?w=600&h=600&fit=crop',
		'https://images.unsplash.com/photo-1559056199-641a0ac8b55e?w=600&h=600&fit=crop',
		'https://images.unsplash.com/photo-1567880905822-56f8e06fe630?w=600&h=600&fit=crop'
	];
</script>

<section class="relative h-[85vh] overflow-hidden md:h-[90vh]">
	<img
		src="https://images.unsplash.com/photo-1554118811-1e0d58224f24?w=1920&h=1080&fit=crop"
		alt="Café Ribeira interior"
		class="absolute inset-0 h-full w-full object-cover"
	/>
	<div class="absolute inset-0 bg-gradient-to-t from-black/70 via-black/40 to-black/20"></div>

	<div class="absolute inset-0 flex items-end pb-12 md:pb-20">
		<div class="container mx-auto max-w-7xl px-4">
			<div class="max-w-2xl text-white">
				<Badge class="mb-4 border-0 bg-accent text-accent-foreground" href="">
					<Clock class="mr-1 h-3 w-3" />
					Open Now
				</Badge>

				<h1 class="font-display mb-4 text-4xl font-bold text-balance md:text-6xl lg:text-7xl">
					Authentic Porto Café Experience
				</h1>

				<p class="font-body mb-6 text-lg text-white/90 md:text-xl">
					Freshly baked pastéis de nata, artisan coffee, and traditional Portuguese brunch in
					historic Ribeira.
				</p>

				<div class="mb-6 grid grid-cols-1 gap-3 sm:grid-cols-2">
					<div
						class="flex items-center gap-3 rounded-lg border border-white/20 bg-black/40 px-4 py-3 backdrop-blur-sm"
					>
						<MapPin class="h-5 w-5 flex-shrink-0 text-primary" />
						<div>
							<p class="font-body text-sm font-semibold">Rua da Ribeira 25</p>
							<p class="font-body text-xs text-white/80">4050-513 Porto</p>
						</div>
					</div>

					<div
						class="flex items-center gap-3 rounded-lg border border-white/20 bg-black/40 px-4 py-3 backdrop-blur-sm"
					>
						<Clock class="h-5 w-5 flex-shrink-0 text-primary" />
						<div>
							<p class="font-body text-sm font-semibold">Mon-Fri: 7AM-8PM</p>
							<p class="font-body text-xs text-white/80">Sat-Sun: 8AM-9PM</p>
						</div>
					</div>
				</div>

				<div class="flex flex-col gap-3 sm:flex-row">
					<Button size="lg" class="text-base" href="/contact">Reserve a Table</Button>
					<Button
						size="lg"
						variant="outline"
						class="border-white/30 bg-white/10 text-base text-white backdrop-blur-sm hover:bg-white/20"
						href="tel:+351220123456"
					>
						<Phone class="mr-2 h-4 w-4" />
						+351 220 123 456
					</Button>
				</div>
			</div>
		</div>
	</div>
</section>

<!-- Menu Preview Section -->
<section class="rustic-texture py-16 md:py-24">
	<div class="container mx-auto max-w-7xl px-4">
		<div class="mb-12 text-center">
			<h2 class="font-display mb-4 text-3xl font-bold md:text-4xl">Menu Favorites</h2>
			<p class="font-body mx-auto max-w-2xl text-lg text-muted-foreground">
				Traditional recipes passed down through generations
			</p>
		</div>

		<div class="mb-8 grid gap-6 md:grid-cols-3">
			{#each menuHighlights as item, index}
				<Card.Root class="border-2 transition-colors hover:border-primary">
					<Card.Content class="p-6">
						<div class="mb-3 flex items-start justify-between">
							<div
								class="flex h-12 w-12 items-center justify-center rounded-full bg-primary/10 text-primary"
							>
								<svelte:component this={item.icon} class="h-5 w-5" />
							</div>
							<span class="font-display text-xl font-bold text-primary">
								{item.price}
							</span>
						</div>
						<h3 class="font-display mb-2 text-xl font-semibold">
							{item.name}
						</h3>
						<p class="font-body text-muted-foreground">
							{item.description}
						</p>
					</Card.Content>
				</Card.Root>
			{/each}
		</div>

		<div class="text-center">
			<Button variant="outline" size="lg" href="/about#menu-section">View Full Menu</Button>
		</div>
	</div>
</section>

<!-- Photo Gallery -->
<section class="bg-muted/30 py-16 md:py-24">
	<div class="container mx-auto max-w-7xl px-4">
		<div class="mb-12 text-center">
			<h2 class="font-display mb-4 text-3xl font-bold md:text-4xl">Our Ambiance</h2>
			<p class="font-body text-lg text-muted-foreground">Step into traditional Portuguese charm</p>
		</div>

		<div class="grid grid-cols-2 gap-3 md:grid-cols-3 md:gap-4">
			{#each galleryImages as image, index}
				<div class="group relative aspect-square cursor-pointer overflow-hidden rounded-lg">
					<img
						src={image}
						alt="Café Ribeira photo {index + 1}"
						class="absolute inset-0 h-full w-full object-cover transition-transform duration-300 group-hover:scale-110"
					/>
				</div>
			{/each}
		</div>
	</div>
</section>

<!-- CTA Section -->
<section class="bg-primary py-16 text-primary-foreground md:py-24">
	<div class="container mx-auto max-w-4xl px-4 text-center">
		<h2 class="font-display mb-6 text-3xl font-bold md:text-5xl">Visit Us Today</h2>
		<p class="font-body mb-8 text-lg opacity-90 md:text-xl">
			Experience authentic Portuguese hospitality in the heart of Porto's historic Ribeira district.
		</p>
		<Button size="lg" variant="secondary" href="/contact">Get Directions & Hours</Button>
	</div>
</section>
