<script>
	import { Button } from '$lib/components/ui/button';
	import { Input } from '$lib/components/ui/input';
	import { Separator } from '$lib/components/ui/separator';

	import australiaImage from '$assets/shared/desktop/illustration-australia.svg';
	import canadaImage from '$assets/shared/desktop/illustration-canada.svg';
	import ukImage from '$assets/shared/desktop/illustration-united-kingdom.svg';

	const locations = [
		{
			image: canadaImage,
			title: 'CANADA'
		},
		{
			image: australiaImage,
			title: 'AUSTRALIA'
		},
		{
			image: ukImage,
			title: 'UNITED KINGDOM'
		}
	];
</script>

<!-- form snippet -->
{#snippet ContactForm()}
	<div class="flex items-center justify-between rounded-2xl bg-pink-cold">
		<div class="m-28 h-fit w-full space-y-7">
			<h1 class="text-5xl font-bold text-white">Contact us</h1>
			<p class="text-sm text-white">
				Ready to take it to the next level? Let’s talk about your project or idea and find out how
				we can help your business grow. If you are looking for unique digital experiences that’s
				relatable to your users, drop us a line.
			</p>
		</div>
		<div class="mb-14 mt-28 h-fit w-full pr-10">
			<form action="?/submit" class="flex h-full w-full flex-col items-end justify-center">
				<Input placeholder="Name" required type="text" class="w-4/5" />
				<Separator class="mb-10 mt-2 w-[85%]" />
				<Input placeholder="Email" type="email" class="w-4/5" />
				<Separator class="mb-10 mt-2 w-[85%]" />
				<Input placeholder="Phone" type="text" class="w-4/5" />
				<Separator class="mb-10 mt-2 w-[85%]" />
				<Input placeholder="message" type="text" class="w-4/5" />
				<Separator class="mb-10 mt-2 w-[85%]" />
				<Button variant="pink" size="sm">Submit</Button>
			</form>
		</div>
	</div>
{/snippet}

<!-- location displayer snippet -->
{#snippet LocationDisplayer({ image, title })}
	<div class="flex h-auto w-full flex-col items-center justify-center space-y-8">
		<img src={image} alt={title} />
		<h1 class="text-1xl font-bold text-pink-cold">{title}</h1>
		<Button variant="darkpink" size="locationButton"
			><a href="/location" class="font-bold">SEE LOCATION</a></Button
		>
	</div>
{/snippet}

<main class="flex h-full w-full flex-col gap-8">
	{@render ContactForm()}
	<div class="flex h-auto w-full items-center justify-center">
		{#each locations as location}
			{@render LocationDisplayer(location)}
		{/each}
	</div>
</main>
