<script>
	import { Button } from '$lib/components/ui/button/';
	import HeroPhone from '$assets/home/desktop/image-hero-phone.png';
</script>

<div class="flex flex-col items-center justify-center space-y-10 px-28">
	<div
		class="relative flex w-full items-center justify-center rounded-[25px] bg-pink-cold px-24 py-40"
	>
		<!-- the right side of the element -->
		<div class="w-3/4 space-y-8">
			<h1 class="text-4xl font-bold text-white">
				Award-winning custom designs and digital branding solutions
			</h1>
			<p class="text-white">
				With over 10 years in the industry, we are experienced in creating fully responsive
				websites, app design, and engaging brand experiences. Find out more about our services.
			</p>
			<Button variant="pink" size="rounded"><p class="font-semibold">Learn more</p></Button>
		</div>
		<div class="h-full w-3/4">
			<img src={HeroPhone} alt="hero phone" />
		</div>
	</div>
	<!-- the phone image section -->
	<div></div>
</div>
