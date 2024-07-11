<script>
	import canadaMap from '$assets/locations/desktop/image-map-canada.png';
	import australiaMap from '$assets/locations/desktop/image-map-australia.png';
	import ukMap from '$assets/locations/desktop/image-map-united-kingdom.png';

	const locationInfoList = [
		{
			image: canadaMap,
			title: 'Canada',
			office: 'Designo Central Office',
			address: '3886 Wellington Street',
			secondAddress: 'Toronto, Ontario M9C 3J5',
			phone: '+1 253-863-8967',
			email: 'contact@designo.co'
		},
		{
			image: australiaMap,
			title: 'Australia',
			office: 'Designo AU Office ',
			address: '19 Balonne Street',
			secondAddress: 'New South Wales 2443',
			phone: '(02) 6720 9092',
			email: 'contact@designo.au'
		},
		{
			image: ukMap,
			title: 'United Kingdom',
			office: 'Designo UK Office ',
			address: '13 Colorado Way',
			secondAddress: 'Rhyd-y-fro SA8 9GA',
			phone: '078 3115 1400',
			email: 'contact@designo.uk'
		}
	];
</script>

{#snippet locationInfo({ image, title, office, address, secondAddress, phone, email }, index)}
	<div
		class="flex h-[350px] w-full items-center justify-between gap-9 {index % 2 == 0
			? 'flex-row-reverse'
			: ''}"
	>
		<div
			class="flex h-full w-3/4 flex-col items-start justify-center gap-y-8 rounded-2xl bg-pink-toocold p-14"
		>
			<h1 class="text-4xl font-bold text-pink-cold">{title}</h1>
			<div class="flex items-center justify-start gap-20">
				<div>
					<h2 class="text-md font-semibold">{office}</h2>
					<p class="text-sm">{address}</p>
					<p class="text-sm">{secondAddress}</p>
				</div>
				<div>
					<h2 class="text-md font-semibold">Contact</h2>
					<p class="text-sm">P: {phone}</p>
					<p class="text-sm">M: {email}</p>
				</div>
			</div>
		</div>
		<img src={image} alt={title} class="size-[350px] rounded-2xl" />
	</div>
{/snippet}
<main class="flex w-full flex-col items-center justify-center gap-16 py-8">
	{#each locationInfoList as location, index}
		{@render locationInfo(location, index)}
	{/each}
</main>
