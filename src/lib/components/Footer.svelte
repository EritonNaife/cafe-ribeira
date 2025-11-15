<script>
	import { Phone, MapPin, Clock, Instagram, Facebook, Mail } from 'lucide-svelte';
</script>

<footer class="rustic-texture border-t border-border bg-card">
	<div class="container mx-auto max-w-7xl px-4 py-12">
		<div class="grid gap-8 md:grid-cols-2 lg:grid-cols-4">
			<div>
				<h3 class="font-display mb-4 text-2xl font-bold text-primary">Café Ribeira</h3>
				<p class="font-body text-sm leading-relaxed text-muted-foreground">
					Traditional Portuguese café in the heart of Porto. Serving authentic pastéis de nata and
					espresso since 1987.
				</p>
			</div>

			<div>
				<h4 class="font-display mb-4 text-lg font-semibold">Contact</h4>
				<ul class="space-y-3">
					<li class="flex items-start gap-2">
						<MapPin class="mt-1 h-4 w-4 flex-shrink-0 text-primary" />
						<span class="font-body text-sm">
							Rua da Ribeira 25<br />
							4050-513 Porto, Portugal
						</span>
					</li>
					<li class="flex items-center gap-2">
						<Phone class="h-4 w-4 flex-shrink-0 text-primary" />
						<a
							href="tel:+351220123456"
							class="font-body text-sm transition-colors hover:text-primary"
						>
							+351 220 123 456
						</a>
					</li>
					<li class="flex items-center gap-2">
						<Mail class="h-4 w-4 flex-shrink-0 text-primary" />
						<a
							href="mailto:hello@caferibeira.pt"
							class="font-body text-sm transition-colors hover:text-primary"
						>
							hello@caferibeira.pt
						</a>
					</li>
				</ul>
			</div>

			<div>
				<h4 class="font-display mb-4 text-lg font-semibold">Hours</h4>
				<ul class="space-y-2">
					<li class="flex items-start gap-2">
						<Clock class="mt-1 h-4 w-4 flex-shrink-0 text-primary" />
						<div class="font-body text-sm">
							<p class="font-semibold">Mon - Fri</p>
							<p class="text-muted-foreground">7:00 AM - 8:00 PM</p>
						</div>
					</li>
					<li class="flex items-start gap-2">
						<Clock class="mt-1 h-4 w-4 flex-shrink-0 text-primary" />
						<div class="font-body text-sm">
							<p class="font-semibold">Sat - Sun</p>
							<p class="text-muted-foreground">8:00 AM - 9:00 PM</p>
						</div>
					</li>
				</ul>
			</div>

			<div>
				<h4 class="font-display mb-4 text-lg font-semibold">Follow Us</h4>
				<div class="mb-6 flex gap-4">
					<a
						href="https://instagram.com"
						target="_blank"
						rel="noopener noreferrer"
						class="flex h-10 w-10 items-center justify-center rounded-full bg-primary text-primary-foreground transition-colors hover:bg-primary/90"
					>
						<Instagram class="h-5 w-5" />
						<span class="sr-only">Instagram</span>
					</a>
					<a
						href="https://facebook.com"
						target="_blank"
						rel="noopener noreferrer"
						class="flex h-10 w-10 items-center justify-center rounded-full bg-primary text-primary-foreground transition-colors hover:bg-primary/90"
					>
						<Facebook class="h-5 w-5" />
						<span class="sr-only">Facebook</span>
					</a>
				</div>
				<nav class="flex flex-col space-y-2">
					<a
						href="/about"
						class="font-body text-sm text-muted-foreground transition-colors hover:text-primary"
					>
						About Us
					</a>
					<a
						href="/contact"
						class="font-body text-sm text-muted-foreground transition-colors hover:text-primary"
					>
						Reservations
					</a>
				</nav>
			</div>
		</div>

		<div class="mt-12 border-t border-border pt-8 text-center">
			<p class="font-body text-sm text-muted-foreground">
				© {new Date().getFullYear()} Café Ribeira. All rights reserved.
			</p>
		</div>
	</div>
</footer>
