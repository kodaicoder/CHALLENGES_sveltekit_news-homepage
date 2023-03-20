<script>
	const newData = [
		{
			id: 'new1',
			title: 'Hydrogen VS Electric Cars',
			paragraph: 'Will hydrogen-fueled cars ever catch up to EVs?'
		},
		{
			id: 'new2',
			title: 'The Downsides of AI Artistry',
			paragraph: 'What are the possible adverse effects of on-demand AI image generation?'
		},
		{
			id: 'new3',
			title: 'Is VC Funding Drying Up?',
			paragraph: 'Private funding by VC firms is down 50% YOY. We take a look at what that means.'
		}
	];
</script>

<div class="bg-veryDarkBlue grid content-start p-6 md:row-span-2 mb-8">
	<h1 class="text-softOrange font-semibold text-4xl">New</h1>
	<ul>
		{#each newData as item}
			<li class="border-b border-grayishBlue py-6">
				<a
					href={`#${item.id}`}
					class="text-offWhite font-bold text-lg leading-loose hover:text-softOrange"
					>{item.title}</a
				>
				<p class="text-sm text-grayishBlue leading-loose">
					{item.paragraph}
				</p>
			</li>
		{/each}
	</ul>
</div>
