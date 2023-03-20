<script>
	import retroPcsImage from '$lib/images/image-retro-pcs.jpg';
	import laptopsImage from '$lib/images/image-top-laptops.jpg';
	import gamingImage from '$lib/images/image-gaming-growth.jpg';

	const footData = [
		{
			link: 'reviving-retro-pcs',
			image: retroPcsImage,
			title: 'Reviving Retro PCs',
			paragraph: 'What happens when old PCs are given modern upgrades?'
		},
		{
			link: 'top-10-laptops-of-2022',
			image: laptopsImage,
			title: 'Top 10 Laptops of 2022',
			paragraph: 'Our best picks for various needs and budgets.'
		},
		{
			link: 'the-growth-of-gaming',
			image: gamingImage,
			title: 'The Growth of Gaming',
			paragraph: 'How the pandemic has sparked fresh opportunities.'
		}
	];
</script>

<div class="grid md:grid-cols-3 md:col-span-3 gap-8">
	{#each footData as item, idx}
		<div class="flex gap-4">
			<img src={item.image} alt={item.title} class="aspect-square object-cover w-1/4" />
			<div class="grid content-between">
				<h1 class="font-bold text-3xl text-grayishBlue">{'0' + (idx + 1)}</h1>
				<a
					href={`#${item.link}`}
					class="text-veryDarkBlue font-bold text-lg leading-loose transition-all duration-200 hover:text-softOrange"
					>{item.title}</a
				>
				<h2 class="font-bold text-veryDarkBlue" />
				<p class="text-sm">{item.paragraph}</p>
			</div>
		</div>
	{/each}
</div>
