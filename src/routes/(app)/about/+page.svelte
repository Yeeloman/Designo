<script>
	import { Button } from '$lib/components/ui/button';

	import ConfrenceTable from '$assets/about/desktop/image-about-hero.jpg';
	import ClassGirl from '$assets/about/desktop/image-world-class-talent.jpg';
	import WallpaperHanger from '$assets/about/desktop/image-real-deal.jpg';

	import australiaImage from '$assets/shared/desktop/illustration-australia.svg';
	import canadaImage from '$assets/shared/desktop/illustration-canada.svg';
	import ukImage from '$assets/shared/desktop/illustration-united-kingdom.svg';

	const CardElements = [
		{
			image: ConfrenceTable,
			title: 'About us',
			description:
				"Founded in 2010, we are a creative agency that produces lasting results for our clients. We’ve partnered with many startups, corporations, and nonprofits alike to craft designs that make real impact. We’re always looking forward to creating brands, products, and digital experiences that connect with our clients' audiences.",
			additionalClasses: 'bg-pink-cold',
			roundCorners: 'rounded-tl-2xl rounded-bl-2xl',
			hTag: 'text-white',
			pTag: 'text-white'
		},
		{
			image: ClassGirl,
			title: 'World-class talent',
			description: `We are a crew of strategists, problem-solvers, and technologists. Every design is thoughtfully crafted from concept to launch, ensuring success in its given market. We are constantly updating our skills in a myriad of platforms.

      Our team is multi-disciplinary and we are not merely interested in form — content and meaning are just as important. We give great importance to craftsmanship, service, and prompt delivery. Clients have always been impressed with our high-quality outcomes that encapsulates their brand’s story and mission.`,
			additionalClasses: 'bg-pink-toocold flex-row-reverse',
			roundCorners: 'rounded-br-2xl rounded-tr-2xl',
			hTag: 'text-pink-cold',
			pTag: ''
		},
		{
			image: WallpaperHanger,
			title: 'The real deal',
			description: `As strategic partners in our clients’ businesses, we are ready to take on any challenge as our own. Solving real problems require empathy and collaboration, and we strive to bring a fresh perspective to every opportunity. We make design and technology more accessible and give you tools to measure success.

      We are visual storytellers in appealing and captivating ways. By combining business and marketing strategies, we inspire audiences to take action and drive real results.`,
			additionalClasses: 'bg-pink-cold',
			roundCorners: 'rounded-tl-2xl rounded-bl-2xl',
			hTag: 'text-white',
			pTag: 'text-white'
		}
	];

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

<!-- Card snippet -->
{#snippet Card({ image, title, description, additionalClasses, hTag, pTag, roundCorners })}
	<div class="flex max-h-fit w-full gap-2 rounded-2xl {additionalClasses}">
		<img src={image} alt={title} class={roundCorners} />
		<div class="flex flex-col items-start justify-center space-y-10 p-20">
			<h1 class=" text-4xl font-bold {hTag}">{title}</h1>
			<p class={pTag}>{description}</p>
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

<main class="space-y-32">
	{#each CardElements as CardElement}
		{@render Card(CardElement)}
	{/each}
	<div class="flex h-auto w-full items-center justify-center">
		{#each locations as location}
			{@render LocationDisplayer(location)}
		{/each}
	</div>
</main>
