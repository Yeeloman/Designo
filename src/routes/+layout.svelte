<script>
	import '../app.css';
	import logoDark from '$lib/assets/shared/desktop/logo-dark.png';
	let { children } = $props();
</script>

<div class="my-10 flex h-[100px] w-full items-center justify-center p-14">
	<div class="w-[15%]"></div>
	<div class="w-[30%] flex-grow">
		<img class="w-[90%]" src={logoDark} alt="Designo Logo" />
	</div>
	<div class="w-4/6"></div>
	<div class="flex w-[45%] space-x-7">
		<a class="font-thin hover:underline hover:underline-offset-8" href="/about">OUR COMPANY</a>
		<a class="font-thin hover:underline hover:underline-offset-8" href="/locations">LOCATONS</a>
		<a class="font-thin hover:underline hover:underline-offset-8" href="/contact">CONTACT</a>
	</div>
	<div class="w-[15%]"></div>
</div>

{@render children()}
