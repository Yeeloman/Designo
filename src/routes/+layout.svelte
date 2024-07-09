<script>
	import '../app.css';
	import logoDark from '$lib/assets/shared/desktop/logo-dark.png';
	let { children } = $props();
</script>

<div class="flex h-[100px] w-full items-center justify-center bg-red-300">
	<div class="w-[15%]"></div>
	<div class="w-[30%] flex-grow">
		<img class="" src={logoDark} alt="Designo Logo" />
	</div>
	<div class="w-4/6"></div>
	<div class="flex w-[45%] space-x-7">
		<a class="hover:underline" href="/about">OUR COMPANY</a>
		<a class="hover:underline" href="/locations">LOCATONS</a>
		<a class="hover:underline" href="/contact">CONTACT</a>
	</div>
	<div class="w-[15%]"></div>
</div>
{@render children()}
