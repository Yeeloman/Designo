<script>
	import { Button } from '$lib/components/ui/button/';
	import HeroPhone from '$assets/home/desktop/image-hero-phone.png';
	import LaptopImage from '$assets/home/desktop/image-web-design-large.jpg';
	import CoolSelfie from '$assets/home/desktop/image-app-design.jpg';
	import GraphicDesign from '$assets/home/desktop/image-graphic-design.jpg';

	import IllPassionate from '$assets/home/desktop/illustration-passionate.svg';
	import IllResourceful from '$assets/home/desktop/illustration-resourceful.svg';
	import IllFriendly from '$assets/home/desktop/illustration-friendly.svg';

	const IllustratorElements = [
		{
			image: IllPassionate,
			title: 'Passionate',
			description:
				'Each project starts with an in-depth brand research to ensure we only create products that serve a purpose. We merge art, design, and technology into exciting new solutions.'
		},
		{
			image: IllResourceful,
			title: 'Resourceful',
			description:
				'Everything that we do has a strategic purpose. We use an agile approach in all of our projects and value customer collaboration. It guarantees superior results that fulfill our clients’ needs.'
		},
		{
			image: IllFriendly,
			title: 'friendly',
			description:
				'We are a group of enthusiastic folks who know how to put people first. Our success depends on our customers, and we strive to give them the best experience a company can provide.'
		}
	];
</script>

{#snippet AwardWinning(phoneImage)}
	<div
		class="mb-10 flex max-h-fit w-full items-center justify-center rounded-[25px] bg-pink-cold pl-24"
	>
		<!-- the right side of the element -->
		<div class="mt-[100px] w-3/4 space-y-8">
			<h1 class="text-4xl font-bold text-white">
				Award-winning custom designs and digital branding solutions
			</h1>
			<p class="text-white">
				With over 10 years in the industry, we are experienced in creating fully responsive
				websites, app design, and engaging brand experiences. Find out more about our services.
			</p>
			<Button variant="pink" size="rounded"><p class="font-semibold">Learn more</p></Button>
		</div>
		<!-- the phone image section -->
		<div class="phone-container max-h-lvh w-full">
			<img src={phoneImage} alt="hero phone" class="-translate-y-[-2%] translate-x-20" />
		</div>
	</div>
{/snippet}

<!-- Card section -->
{#snippet Card(image, title)}
	<div
		class="relative flex h-full w-full flex-col items-center justify-center rounded-lg border-none"
	>
		<img src={image} alt="laptop" class="rounded-2xl" />
		<div
			class="absolute inset-0 rounded-2xl bg-[#f7d6ce] opacity-0 transition-opacity hover:opacity-50"
		></div>
		<div class="absolute space-y-2">
			<h1 class=" text-5xl font-bold text-white">{title} DESIGN</h1>
			<p class="absolute text-xl font-bold text-white">
				<a href="/webdesign">VIEW PROJECTS <span class="font-bold text-red-300">></span> </a>
			</p>
		</div>
	</div>
{/snippet}

<!-- Grid Div section -->
{#snippet GridDiv()}
	<div class="grid grid-cols-2 space-x-5">
		{@render Card(LaptopImage, 'WEB')}
		<div class="grid-col-1 grid">
			{@render Card(CoolSelfie, 'APP')}
			{@render Card(GraphicDesign, 'GRAPHIC')}
		</div>
	</div>
{/snippet}

<!-- Illustrations section -->
{#snippet Illustrators(element)}
	<div class="flex h-auto w-full flex-col items-center justify-center space-y-8">
		<img src={element.image} alt="a passionate illustartor" />
		<h1 class="text-1xl font-bold">{element.title}</h1>
		<p class="text-balance text-center text-sm font-thin text-gray-700">
			{element.description}
		</p>
	</div>
{/snippet}

<main class="flex flex-col items-center justify-center space-y-24">
	{@render AwardWinning(HeroPhone)}
	{@render GridDiv()}
	<div class="flex h-auto w-full items-center justify-center">
		{#each IllustratorElements as element}
			{@render Illustrators(element)}
		{/each}
	</div>
</main>

<style>
	.phone-container {
		clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%);
	}
</style>
