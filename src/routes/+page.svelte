<script>
	import { Button } from '$lib/components/ui/button/';
	import HeroPhone from '$assets/home/desktop/image-hero-phone.png';
	import LaptopImage from '$assets/home/desktop/image-web-design-large.jpg';
	import CoolSelfie from '$assets/home/desktop/image-app-design.jpg';
	import GraphicDesign from '$assets/home/desktop/image-graphic-design.jpg';
</script>

{#snippet AwardWinning(phoneImage)}
	<div class="flex max-h-fit w-full items-center justify-center rounded-[25px] bg-pink-cold pl-24">
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

{#snippet Card(image, title)}
	<!-- card section -->
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

<main class="flex flex-col items-center justify-center space-y-40">
	{@render AwardWinning(HeroPhone)}
	<div class="grid grid-cols-2 space-x-5">
		{@render Card(LaptopImage, 'WEB')}
		<div class="grid-col-1 grid">
			{@render Card(CoolSelfie, 'APP')}
			{@render Card(GraphicDesign, 'GRAPHIC')}
		</div>
	</div>
</main>

<style>
	.phone-container {
		clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%);
	}
</style>
