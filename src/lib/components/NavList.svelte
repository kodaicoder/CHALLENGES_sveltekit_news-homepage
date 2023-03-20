<script>
	import { createEventDispatcher } from 'svelte';
	import { page } from '$app/stores';
	export let text = 'default_text';
	export let href = '#';

	const dispatcher = createEventDispatcher();

	function linkClick() {
		dispatcher('linkClick');
	}
</script>

<li>
	<!--? Note : in real project you should to using `$page.url.pathname` instead of `$page.url.hash` -->
	<a
		on:click={linkClick}
		class="block text-black font-semibold md:text-sm md:text-darkGrayishBlue md:font-normal p-4  rounded-lg transition-all duration-300 hover:text-softOrange
		 {$page.url.hash === `${href}` ? '!text-softOrange bg-veryDarkBlue ml-0' : ''}"
		{href}
	>
		{text}
	</a>
</li>
