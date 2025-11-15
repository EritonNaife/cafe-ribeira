<script>
	import { Phone, MapPin, Mail, Clock, Instagram, Facebook } from 'lucide-svelte';
	import { Button } from '$lib/components/ui/button/index.js';
	import { Input } from '$lib/components/ui/input/index.js';
	import { Textarea } from '$lib/components/ui/textarea/index.js';
	import { Label } from '$lib/components/ui/label/index.js';
	import * as Card from '$lib/components/ui/card/index.js';
	import * as Select from '$lib/components/ui/select/index.js';
	import * as Accordion from '$lib/components/ui/accordion/index.js';

	let formData = {
		name: '',
		email: '',
		phone: '',
		date: '',
		time: '',
		guests: '',
		message: ''
	};

	/**
	 * @param {{ preventDefault: () => void; }} e
	 */
	function handleSubmit(e) {
		e.preventDefault();
		alert('Reservation request submitted! We will contact you shortly to confirm.');
		formData = {
			name: '',
			email: '',
			phone: '',
			date: '',
			time: '',
			guests: '',
			message: ''
		};
	}

	const faqs = [
		{
			question: 'Do I need a reservation?',
			answer:
				'Reservations are recommended, especially for weekends and brunch hours. However, we also welcome walk-ins and will do our best to accommodate you.'
		},
		{
			question: 'Do you have vegetarian and vegan options?',
			answer:
				'Yes! We offer several vegetarian options and can accommodate vegan diets. Please let us know your dietary requirements when making a reservation.'
		},
		{
			question: 'Is there parking nearby?',
			answer:
				'Street parking is available in the Ribeira area. We recommend the public parking at Praça da Ribeira, just a 2-minute walk from our café.'
		},
		{
			question: 'Do you accept credit cards?',
			answer: 'Yes, we accept all major credit cards, Multibanco, and cash.'
		},
		{
			question: 'Can you accommodate large groups?',
			answer:
				'We can accommodate groups of up to 15 people. For parties larger than 8, please contact us in advance so we can prepare the best seating arrangement.'
		},
		{
			question: 'Do you offer takeaway?',
			answer:
				'Yes! All our pastries, sandwiches, and beverages are available for takeaway. Call ahead to place your order.'
		},
		{
			question: 'Is the café wheelchair accessible?',
			answer:
				'Yes, our café is fully wheelchair accessible with a step-free entrance and accessible restroom facilities.'
		},
		{
			question: 'Do you have Wi-Fi?',
			answer: 'Yes, we offer complimentary Wi-Fi to all our guests. Ask our staff for the password.'
		}
	];
</script>

<svelte:head>
	<title>Contact & Reservations - Café Ribeira</title>
</svelte:head>

<!-- Hero Section -->
<section class="rustic-texture relative bg-primary py-12 text-primary-foreground md:py-20">
	<div class="container mx-auto max-w-7xl px-4 text-center">
		<h1 class="font-display mb-4 text-4xl font-bold md:text-6xl">Visit Us</h1>
		<p class="font-body mx-auto max-w-2xl text-lg opacity-90 md:text-xl">
			We'd love to welcome you to Café Ribeira. Reserve a table or stop by for a coffee.
		</p>
	</div>
</section>

<!-- Contact Info & Reservation Form -->
<section class="py-16 md:py-24">
	<div class="container mx-auto max-w-7xl px-4">
		<div class="grid gap-12 lg:grid-cols-2">
			<!-- Contact Information -->
			<div class="space-y-8">
				<div>
					<h2 class="font-display mb-6 text-3xl font-bold">Get In Touch</h2>

					<div class="space-y-6">
						<!-- Address -->
						<Card.Root>
							<Card.Content class="p-6">
								<div class="flex items-start gap-4">
									<div
										class="flex h-12 w-12 flex-shrink-0 items-center justify-center rounded-full bg-primary/10"
									>
										<MapPin class="h-6 w-6 text-primary" />
									</div>
									<div>
										<h3 class="font-display mb-1 text-lg font-semibold">Location</h3>
										<p class="font-body text-muted-foreground">
											Rua da Ribeira 25<br />
											4050-513 Porto, Portugal
										</p>
										<Button
											variant="link"
											class="mt-2 px-0"
											href="https://maps.google.com/?q=Rua+da+Ribeira+25+Porto"
											target="_blank"
											rel="noopener noreferrer"
										>
											Get Directions →
										</Button>
									</div>
								</div>
							</Card.Content>
						</Card.Root>

						<!-- Hours -->
						<Card.Root>
							<Card.Content class="p-6">
								<div class="flex items-start gap-4">
									<div
										class="flex h-12 w-12 flex-shrink-0 items-center justify-center rounded-full bg-primary/10"
									>
										<Clock class="h-6 w-6 text-primary" />
									</div>
									<div class="flex-grow">
										<h3 class="font-display mb-3 text-lg font-semibold">Opening Hours</h3>
										<div class="font-body space-y-2">
											<div class="flex justify-between">
												<span class="text-muted-foreground">Monday - Friday</span>
												<span class="font-semibold">7:00 AM - 8:00 PM</span>
											</div>
											<div class="flex justify-between">
												<span class="text-muted-foreground">Saturday</span>
												<span class="font-semibold">8:00 AM - 9:00 PM</span>
											</div>
											<div class="flex justify-between">
												<span class="text-muted-foreground">Sunday</span>
												<span class="font-semibold">8:00 AM - 9:00 PM</span>
											</div>
										</div>
									</div>
								</div>
							</Card.Content>
						</Card.Root>

						<!-- Phone & Email -->
						<Card.Root>
							<Card.Content class="p-6">
								<div class="space-y-4">
									<div class="flex items-center gap-4">
										<div
											class="flex h-12 w-12 flex-shrink-0 items-center justify-center rounded-full bg-primary/10"
										>
											<Phone class="h-6 w-6 text-primary" />
										</div>
										<div>
											<h3 class="font-display mb-1 text-lg font-semibold">Phone</h3>
											<a
												href="tel:+351220123456"
												class="font-body text-muted-foreground transition-colors hover:text-primary"
											>
												+351 220 123 456
											</a>
										</div>
									</div>

									<div class="flex items-center gap-4">
										<div
											class="flex h-12 w-12 flex-shrink-0 items-center justify-center rounded-full bg-primary/10"
										>
											<Mail class="h-6 w-6 text-primary" />
										</div>
										<div>
											<h3 class="font-display mb-1 text-lg font-semibold">Email</h3>
											<a
												href="mailto:hello@caferibeira.pt"
												class="font-body text-muted-foreground transition-colors hover:text-primary"
											>
												hello@caferibeira.pt
											</a>
										</div>
									</div>
								</div>
							</Card.Content>
						</Card.Root>

						<!-- Social Media -->
						<Card.Root>
							<Card.Content class="p-6">
								<h3 class="font-display mb-4 text-lg font-semibold">Follow Us</h3>
								<div class="flex gap-3">
									<Button
										variant="outline"
										size="icon"
										href="https://instagram.com"
										target="_blank"
										rel="noopener noreferrer"
									>
										<Instagram class="h-5 w-5" />
									</Button>
									<Button
										variant="outline"
										size="icon"
										href="https://facebook.com"
										target="_blank"
										rel="noopener noreferrer"
									>
										<Facebook class="h-5 w-5" />
									</Button>
								</div>
							</Card.Content>
						</Card.Root>
					</div>
				</div>
			</div>

			<!-- Reservation Form -->
			<div>
				<Card.Root>
					<Card.Header>
						<Card.Title class="font-display text-2xl">Reserve a Table</Card.Title>
						<Card.Description class="font-body">
							Fill out the form below and we'll confirm your reservation shortly.
						</Card.Description>
					</Card.Header>
					<Card.Content>
						<form on:submit={handleSubmit} class="space-y-6">
							<div class="space-y-2">
								<Label for="name">Full Name *</Label>
								<Input id="name" bind:value={formData.name} required placeholder="Maria Silva" />
							</div>

							<div class="grid gap-4 sm:grid-cols-2">
								<div class="space-y-2">
									<Label for="email">Email *</Label>
									<Input
										id="email"
										type="email"
										bind:value={formData.email}
										required
										placeholder="maria@example.com"
									/>
								</div>

								<div class="space-y-2">
									<Label for="phone">Phone *</Label>
									<Input
										id="phone"
										type="tel"
										bind:value={formData.phone}
										required
										placeholder="+351 912 345 678"
									/>
								</div>
							</div>

							<div class="grid gap-4 sm:grid-cols-2">
								<div class="space-y-2">
									<Label for="date">Date *</Label>
									<Input id="date" type="date" bind:value={formData.date} required />
								</div>

								<div class="space-y-2">
									<Label for="time">Time *</Label>
									<!--
                                    <Select.Root bind:value={formData.time}>
										<Select.Trigger id="time">
											<Select.Value placeholder="Select time" />
										</Select.Trigger>

										<Select.Content>
											<Select.Viewport>
												<Select.Group>
													<Select.Item value="7:00">7:00 AM</Select.Item>
													<Select.Item value="8:00">8:00 AM</Select.Item>
													<Select.Item value="9:00">9:00 AM</Select.Item>
													<Select.Item value="10:00">10:00 AM</Select.Item>
													<Select.Item value="11:00">11:00 AM</Select.Item>
													<Select.Item value="12:00">12:00 PM</Select.Item>
													<Select.Item value="13:00">1:00 PM</Select.Item>
													<Select.Item value="14:00">2:00 PM</Select.Item>
													<Select.Item value="15:00">3:00 PM</Select.Item>
													<Select.Item value="16:00">4:00 PM</Select.Item>
													<Select.Item value="17:00">5:00 PM</Select.Item>
													<Select.Item value="18:00">6:00 PM</Select.Item>
													<Select.Item value="19:00">7:00 PM</Select.Item>
												</Select.Group>
											</Select.Viewport>
										</Select.Content>
									</Select.Root>
                                    -->
								</div>
							</div>

							<div class="space-y-2">
								<Label for="guests">Number of Guests *</Label>

								<!--
                                	<Select.Root bind:value={formData.guests}>
									<Select.Trigger id="guests">
										<Select.Value placeholder="Select guests" />
									</Select.Trigger>

									<Select.Content>
										<Select.Viewport>
											<Select.Group>
												<Select.Item value="1">1 Guest</Select.Item>
												<Select.Item value="2">2 Guests</Select.Item>
												<Select.Item value="3">3 Guests</Select.Item>
												<Select.Item value="4">4 Guests</Select.Item>
												<Select.Item value="5">5 Guests</Select.Item>
												<Select.Item value="6">6 Guests</Select.Item>
												<Select.Item value="7">7 Guests</Select.Item>
												<Select.Item value="8">8 Guests</Select.Item>
												<Select.Item value="9+">9+ Guests</Select.Item>
											</Select.Group>
										</Select.Viewport>
									</Select.Content>
								</Select.Root>
                                
                                -->
							</div>

							<div class="space-y-2">
								<Label for="message">Special Requests</Label>
								<Textarea
									id="message"
									bind:value={formData.message}
									placeholder="Allergies, dietary restrictions, special occasions..."
									rows={4}
								/>
							</div>

							<Button type="submit" size="lg" class="w-full">Submit Reservation</Button>

							<p class="text-center text-sm text-muted-foreground">
								We'll confirm your reservation via email or phone within 24 hours.
							</p>
						</form>
					</Card.Content>
				</Card.Root>
			</div>
		</div>
	</div>
</section>

<!-- Map Section -->
<section class="bg-muted/30 py-16">
	<div class="container mx-auto max-w-7xl px-4">
		<h2 class="font-display mb-8 text-center text-3xl font-bold">Find Us</h2>
		<div class="aspect-[16/9] w-full overflow-hidden rounded-lg shadow-lg md:aspect-[21/9]">
			<iframe
				src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3004.478843284472!2d-8.614486!3d41.140859!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0xd2465abc4e153c1%3A0xa648d95640b114bc!2sRibeira%2C%20Porto%2C%20Portugal!5e0!3m2!1sen!2sus!4v1234567890"
				width="100%"
				height="100%"
				style="border: 0"
				allowfullscreen
				loading="lazy"
				referrerpolicy="no-referrer-when-downgrade"
				title="Café Ribeira Location"
			></iframe>
		</div>
	</div>
</section>

<!-- FAQ Section -->
<section class="rustic-texture py-16 md:py-24">
	<div class="container mx-auto max-w-4xl px-4">
		<div class="mb-12 text-center">
			<h2 class="font-display mb-4 text-3xl font-bold md:text-4xl">Frequently Asked Questions</h2>
			<p class="font-body text-lg text-muted-foreground">
				Everything you need to know about visiting us
			</p>
		</div>

		<Accordion.Root type="single" collapsible class="space-y-4">
			{#each faqs as faq, index}
				<Accordion.Item value="item-{index}" class="rounded-lg border border-border bg-card px-6">
					<Accordion.Trigger class="font-display py-4 text-lg font-semibold hover:no-underline">
						{faq.question}
					</Accordion.Trigger>
					<Accordion.Content class="font-body pb-4 text-muted-foreground">
						{faq.answer}
					</Accordion.Content>
				</Accordion.Item>
			{/each}
		</Accordion.Root>

		<div class="mt-12 text-center">
			<p class="font-body mb-4 text-muted-foreground">Still have questions?</p>
			<Button variant="outline" href="mailto:hello@caferibeira.pt">
				<Mail class="mr-2 h-4 w-4" />
				Email Us
			</Button>
		</div>
	</div>
</section>
