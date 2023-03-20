<script>
	import web3Desktop from '$lib/images/image-web-3-desktop.jpg';
	import web3Mobile from '$lib/images/image-web-3-mobile.jpg';
</script>

<div class="grid gap-8 mt-8 md:col-span-2 md:m-0 md:row-span-2 md:grid-cols-2 mb-8">
	<div class="md:col-span-2 ">
		<picture>
			<source srcset={web3Desktop} media="(min-width:1024px)" />
			<img src={web3Mobile} alt="web3" />
		</picture>
	</div>
	<div>
		<h1 class="font-extrabold text-6xl text-black">The Bright Future of Web 3.0?</h1>
	</div>
	<div class="flex flex-col justify-between items-start">
		<p class="text-sm  leading-normal">
			We dive into the next evolution of the web that claims to put the power of the platforms back
			into the hands of the people. But is it really fulfilling its promise?
		</p>
		<button
			class="mt-8 tracking-[0.3em] p-3 px-8 font-medium text-sm text-white bg-softRed transition-all duration-200 hover:bg-black hover:text-white "
			>READ MORE</button
		>
	</div>
</div>
