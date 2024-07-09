<script>
	import '../app.css';
	import { Button } from '$lib/components/ui/button';
	import logoDark from '$assets/shared/desktop/logo-dark.png';
	let { children } = $props();
</script>

<svelte:head>
	<title>designo: Home</title>
</svelte:head>

{#snippet header(logo, underlineOffset)}
	<div class="flex h-[100px] w-[80%] items-center justify-between">
		<div class="w-[20%]">
			<a href="/">
				<img class="w-[90%]" src={logo} alt="Designo Logo" />
			</a>
		</div>
		<div class="flex w-auto space-x-7">
			<a class="font-thin hover:underline {underlineOffset}" href="/about">OUR COMPANY</a>
			<a class="font-thin hover:underline {underlineOffset}" href="/locations">LOCATONS</a>
			<a class="font-thin hover:underline {underlineOffset}" href="/contact">CONTACT</a>
		</div>
	</div>
{/snippet}

{#snippet footer()}
	<div class="flex w-[80%] items-center justify-center rounded-2xl bg-[#E78168] p-16">
		<div class="w-3/4 font-semibold text-white">
			<h1 class="m-5 w-[60%] text-4xl">Let’s talk about your project</h1>
			<p class="m-5 w-[70%] text-sm">
				Ready to take it to the next level? Contact us today and find out how our expertise can help
				your business grow.
			</p>
		</div>
		<div class="w-1/4">
			<Button
				class="bg-white p-10 text-base text-black hover:bg-[#ffad9b] hover:text-white"
				href="/contact">Get in touch</Button
			>
		</div>
	</div>
{/snippet}

<!-- main content -->
<div class=" m-[2%] flex flex-col items-center justify-center">
	{@render header(logoDark, 'underline-offset-8')}
	{@render children()}
	{@render footer()}
</div>
