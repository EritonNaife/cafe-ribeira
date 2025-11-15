<script>
	import { Leaf, WheatOff, Milk } from 'lucide-svelte';
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import { Button } from '$lib/components/ui/button/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import * as Card from '$lib/components/ui/card/index.js';
	import { Separator } from '$lib/components/ui/separator/index.js';

	const menuSections = [
		{
			category: 'Breakfast',
			items: [
				{
					name: 'Continental Breakfast',
					description: 'Fresh croissants, butter, jam, orange juice, and coffee',
					price: '€6.50',
					dietary: ['vegetarian']
				},
				{
					name: 'Tosta Mista',
					description: 'Traditional Portuguese ham and cheese toast',
					price: '€4.20',
					dietary: []
				},
				{
					name: 'Açorda de Gambas',
					description: 'Bread stew with shrimp, garlic, and coriander',
					price: '€12.50',
					dietary: ['gluten-free-option']
				}
			]
		},
		{
			category: 'Pastries',
			items: [
				{
					name: 'Pastel de Nata',
					description: 'Classic Portuguese custard tart with cinnamon',
					price: '€1.50',
					dietary: ['vegetarian']
				},
				{
					name: 'Bola de Berlim',
					description: 'Cream-filled doughnut dusted with sugar',
					price: '€1.80',
					dietary: ['vegetarian']
				},
				{
					name: 'Pão de Deus',
					description: 'Sweet bread rolls with coconut topping',
					price: '€1.40',
					dietary: ['vegetarian']
				}
			]
		},
		{
			category: 'Lunch & Brunch',
			items: [
				{
					name: 'Francesinha',
					description: "Porto's famous sandwich with melted cheese and spicy sauce",
					price: '€9.50',
					dietary: []
				},
				{
					name: 'Bacalhau à Brás',
					description: 'Shredded cod with potatoes, eggs, and olives',
					price: '€11.00',
					dietary: ['gluten-free']
				},
				{
					name: 'Salada de Polvo',
					description: 'Octopus salad with olive oil, coriander, and onions',
					price: '€13.50',
					dietary: ['gluten-free', 'dairy-free']
				}
			]
		},
		{
			category: 'Beverages',
			items: [
				{
					name: 'Café Expresso',
					description: 'Traditional Portuguese espresso',
					price: '€0.80',
					dietary: ['vegan']
				},
				{
					name: 'Galão',
					description: 'Coffee with hot milk, served in a tall glass',
					price: '€1.50',
					dietary: ['vegetarian']
				},
				{
					name: 'Vinho do Porto',
					description: 'Selection of Port wines',
					price: '€4.50',
					dietary: ['vegan']
				}
			]
		}
	];

	const ambiance = [
		'https://images.unsplash.com/photo-1554118811-1e0d58224f24?w=800&h=600&fit=crop',
		'https://images.unsplash.com/photo-1559056199-641a0ac8b55e?w=800&h=600&fit=crop',
		'https://images.unsplash.com/photo-1501492673258-6d4447d2f4b6?w=800&h=600&fit=crop',
		'https://images.unsplash.com/photo-1511920170033-f8396924c348?w=800&h=600&fit=crop'
	];

	/**
	 * @param {string} label
	 */
	function getDietaryLabel(label) {
		switch (label) {
			case 'vegetarian':
				return 'V';
			case 'gluten-free':
				return 'GF';
			case 'gluten-free-option':
				return 'GF*';
			case 'dairy-free':
				return 'DF';
			case 'vegan':
				return 'VG';
			default:
				return '';
		}
	}
</script>

<svelte:head>
	<title>Our Story & Menu - Café Ribeira</title>
</svelte:head>

<!-- Hero Section -->
<section class="relative h-[40vh] overflow-hidden md:h-[50vh]">
	<img
		src="https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?w=1920&h=1080&fit=crop"
		alt="Café interior"
		class="absolute inset-0 h-full w-full object-cover"
	/>
	<div class="absolute inset-0 bg-gradient-to-t from-black/70 via-black/40 to-transparent" />

	<div class="absolute inset-0 flex items-end pb-12">
		<div class="container mx-auto max-w-7xl px-4">
			<h1 class="font-display mb-4 text-4xl font-bold text-white md:text-6xl">Our Story & Menu</h1>
		</div>
	</div>
</section>

<!-- Story Section -->
<section class="rustic-texture py-16 md:py-24">
	<div class="container mx-auto max-w-4xl px-4">
		<div class="prose prose-lg max-w-none">
			<h2 class="font-display mb-6 text-center text-3xl font-bold md:text-4xl">
				A Tradition Since 1987
			</h2>

			<div class="font-body space-y-6 leading-relaxed text-muted-foreground">
				<p>
					Nestled in the cobblestone streets of Porto's historic Ribeira district, Café Ribeira has
					been serving the community for over three decades. What started as a small family bakery
					has grown into a beloved neighborhood gathering place.
				</p>

				<p>
					Our founder, Maria Santos, learned the art of pastry-making from her grandmother in a
					small village outside Porto. She brought those time-honored recipes to the city, where
					they've delighted locals and visitors alike.
				</p>

				<p>
					Every morning, we wake before dawn to prepare our famous pastéis de nata using the
					original recipe. The smell of fresh bread, strong espresso, and cinnamon fills our café,
					welcoming neighbors starting their day and tourists discovering authentic Portuguese
					flavors.
				</p>

				<p class="font-semibold text-foreground">
					Today, three generations of the Santos family continue the tradition, ensuring every
					visitor experiences the warmth and hospitality that define Portuguese café culture.
				</p>
			</div>
		</div>
	</div>
</section>

<!-- Menu Section -->
<section id="menu-section" class="bg-muted/30 py-16 md:py-24">
	<div class="container mx-auto max-w-6xl px-4">
		<div class="mb-12 text-center">
			<h2 class="font-display mb-4 text-3xl font-bold md:text-4xl">Our Menu</h2>
			<p class="font-body mb-6 text-lg text-muted-foreground">
				Traditional Portuguese dishes made with love and fresh ingredients
			</p>

			<!-- Dietary Legend -->
			<div class="flex flex-wrap justify-center gap-4 text-sm">
				<div class="flex items-center gap-1">
					<Badge variant="outline" class="bg-background">
						<Leaf class="mr-1 h-3 w-3" />
						V - Vegetarian
					</Badge>
				</div>
				<div class="flex items-center gap-1">
					<Badge variant="outline" class="bg-background">
						<Leaf class="mr-1 h-3 w-3" />
						VG - Vegan
					</Badge>
				</div>
				<div class="flex items-center gap-1">
					<Badge variant="outline" class="bg-background">
						<WheatOff class="mr-1 h-3 w-3" />
						GF - Gluten Free
					</Badge>
				</div>
				<div class="flex items-center gap-1">
					<Badge variant="outline" class="bg-background">
						<Milk class="mr-1 h-3 w-3" />
						DF - Dairy Free
					</Badge>
				</div>
			</div>
		</div>

		<!-- Menu Items -->
		<div class="space-y-12">
			{#each menuSections as section, sectionIndex}
				<div>
					<h3 class="font-display mb-6 text-2xl font-bold text-primary md:text-3xl">
						{section.category}
					</h3>

					<div class="space-y-4">
						{#each section.items as item, itemIndex}
							<Card.Root class="transition-shadow hover:shadow-md">
								<Card.Content class="p-6">
									<div class="flex items-start justify-between gap-4">
										<div class="flex-grow">
											<div class="mb-2 flex items-center gap-2">
												<h4 class="font-display text-lg font-semibold">
													{item.name}
												</h4>
												{#if item.dietary.length > 0}
													<div class="flex gap-1">
														{#each item.dietary as diet}
															<Badge variant="secondary" class="px-1.5 py-0.5 text-xs">
																{getDietaryLabel(diet)}
															</Badge>
														{/each}
													</div>
												{/if}
											</div>
											<p class="font-body text-sm text-muted-foreground">
												{item.description}
											</p>
										</div>
										<span class="font-display flex-shrink-0 text-lg font-bold text-primary">
											{item.price}
										</span>
									</div>
								</Card.Content>
							</Card.Root>
						{/each}
					</div>

					{#if sectionIndex < menuSections.length - 1}
						<Separator class="mt-8" />
					{/if}
				</div>
			{/each}
		</div>

		<div class="mt-12 text-center">
			<p class="font-body mb-6 text-sm text-muted-foreground">
				Prices include VAT. Menu items subject to availability.
			</p>
			<Button size="lg" href="/contact">Reserve Your Table</Button>
		</div>
	</div>
</section>

<!-- Ambiance Gallery -->
<section class="rustic-texture py-16 md:py-24">
	<div class="container mx-auto max-w-7xl px-4">
		<div class="mb-12 text-center">
			<h2 class="font-display mb-4 text-3xl font-bold md:text-4xl">Our Space</h2>
			<p class="font-body text-lg text-muted-foreground">
				Experience the warm, rustic charm of traditional Porto
			</p>
		</div>

		<div class="grid gap-4 md:grid-cols-2">
			{#each ambiance as image, index}
				<div class="group relative aspect-[4/3] overflow-hidden rounded-lg">
					<img
						src={image}
						alt="Café ambiance {index + 1}"
						class="absolute inset-0 h-full w-full object-cover transition-transform duration-300 group-hover:scale-105"
					/>
				</div>
			{/each}
		</div>
	</div>
</section>
