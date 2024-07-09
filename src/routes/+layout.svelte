<script>
	import '../app.css';
	import { Button } from '$lib/components/ui/button';
	import { Separator } from '$lib/components/ui/separator';
	import logoDark from '$assets/shared/desktop/logo-dark.png';
	import logoLight from '$assets/shared/desktop/logo-light.png';
	import Icon from '@iconify/svelte';
	let { children } = $props();

	const iconStyles = 'w-8 h-8 text-pink-cold';
</script>

<svelte:head>
	<title>designo: Home</title>
</svelte:head>

{#snippet header(logo, additionalClasses)}
	<div class="flex h-[100px] w-[80%] items-center justify-between">
		<div class="w-[20%]">
			<a href="/">
				<img class="w-[90%]" src={logo} alt="Designo Logo" />
			</a>
		</div>
		<div class="flex w-auto space-x-7">
			<a class="font-thin {additionalClasses}" href="/about">OUR COMPANY</a>
			<a class="font-thin {additionalClasses}" href="/locations">LOCATONS</a>
			<a class="font-thin {additionalClasses}" href="/contact">CONTACT</a>
		</div>
	</div>
{/snippet}

{#snippet footer()}
	<!-- this is the get in touch section -->
	<div class="top-0 flex w-[80%] items-center justify-center rounded-2xl bg-pink-cold p-16">
		<div class="w-3/4 font-semibold text-white">
			<h1 class="m-5 w-[60%] text-4xl">Let’s talk about your project</h1>
			<p class="m-5 w-[70%] text-sm">
				Ready to take it to the next level? Contact us today and find out how our expertise can help
				your business grow.
			</p>
			<p></p>
		</div>
		<div class="w-1/4">
			<Button variant="pink" size="default" href="/contact">Get in touch</Button>
		</div>
	</div>
	<!-- this is the contact and social section -->
	<div class="flex w-full flex-col items-center justify-center bg-coldblack p-[5%]">
		{@render header(logoLight, 'text-white')}
		<Separator class="w-[80%] bg-gray-500" />
		<div class="mt-10 flex w-[80%] items-center justify-between text-white">
			<div>
				<p>Designo Central Office</p>
				<p>3886 Wellington Street</p>
				<p>Toronto, Ontario M9C 3J5</p>
			</div>
			<div>
				<p>Contact Us (Central Office)</p>
				<p>P : +1 253-863-8967</p>
				<p>M : contact@designo.co</p>
			</div>
			<div class="flex items-center justify-between space-x-12">
				<Icon icon="ri:facebook-box-fill" class={iconStyles} />
				<Icon icon="mdi:instagram" class={iconStyles} />
				<Icon icon="bi:twitter-x" class={iconStyles} />
				<Icon icon="teenyicons:pinterest-solid" class={iconStyles} />
				<Icon icon="mdi:youtube" class={iconStyles} />
			</div>
		</div>
	</div>
{/snippet}

<!-- main content -->
<div class=" m-[2%] flex flex-col items-center justify-center">
	{@render header(logoDark, 'hover:underline underline-offset-8')}
	{@render children()}
</div>
<div class="relative flex flex-col items-center justify-center">
	{@render footer()}
</div>
