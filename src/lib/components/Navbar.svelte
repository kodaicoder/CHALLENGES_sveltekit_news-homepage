<script>
	import { browser } from '$app/environment';
	import { slide, fade } from 'svelte/transition';
	import logoImg from '$lib/images/logo.svg';
	import NavList from './NavList.svelte';

	import menuImg from '$lib/images/icon-menu.svg';
	import closeImg from '$lib/images/icon-menu-close.svg';
	let menuShow = false;
	let innerWidth = 0;

	//? made body no longer scrolls when a side nav is open
	//? and the scroll location is maintained both
	//? when a side nav is open or closed.
	$: {
		if (browser) {
			window.addEventListener('scroll', () => {
				document.documentElement.style.setProperty('--scroll-y', `${window.scrollY}px`);
			});
			if (menuShow) {
				const scrollY = document.documentElement.style.getPropertyValue('--scroll-y');
				const body = document.body;
				body.style.position = 'fixed';
				body.style.top = `-${scrollY}`;
			} else {
				const body = document.body;
				const scrollY = body.style.top;
				body.style.position = '';
				body.style.top = '';
				window.scrollTo(0, parseInt(scrollY || '0') * -1);
			}
		}
	}

	//? fix issue while user adjust width of page and didn't close side nav menu
	$: {
		if (innerWidth > 768) {
			menuShow = false;
		}
	}

	const closeSideNav = () => {
		menuShow = false;
	};
</script>

<svelte:window bind:innerWidth />

<div class="md:relative w-full p-4 fixed top-0 left-0 bg-white  grid grid-cols-2  items-center ">
	<a href="#/" class="w-fit">
		<img src={logoImg} alt="Logo" />
	</a>
	<!-- burger menu -->
	<div class="flex md:hidden justify-end h-full overflow-hidden">
		<button on:click={() => (menuShow = !menuShow)}>
			<img src={menuImg} alt="menu" class="  aspect-square" />
		</button>
	</div>

	<!-- normal nav -->
	<ul class="hidden md:flex justify-end gap-4">
		<NavList text="Home" href="#home" />
		<NavList text="New" href="#new" />
		<NavList text="Popular" href="#popular" />
		<NavList text="Trending" href="#trending" />
		<NavList text="Categories" href="#categories" />
	</ul>
</div>

<!-- side nav -->
{#if menuShow}
	<!-- Backdrop -->
	<div class="md:hidden">
		<button
			transition:fade
			on:click={closeSideNav}
			class="fixed top-0 right-0 w-full h-full backdrop-brightness-50 z-20 overflow-hidden"
		/>
		<!-- Menu -->
		<div
			transition:slide={{ duration: 300, axis: 'x' }}
			class="fixed top-0 right-0 bg-white w-3/5 h-full z-30 overflow-hidden"
		>
			<div class="flex">
				<button class="ml-auto m-4" on:click={closeSideNav}>
					<img src={closeImg} alt="close" />
				</button>
			</div>
			<div class="p-4">
				<ul class="flex flex-col mt-12">
					<NavList text="Home" href="#home" on:linkClick={closeSideNav} />
					<NavList text="New" href="#new" on:linkClick={closeSideNav} />
					<NavList text="Popular" href="#popular" on:linkClick={closeSideNav} />
					<NavList text="Trending" href="#trending" on:linkClick={closeSideNav} />
					<NavList text="Categories" href="#categories" on:linkClick={closeSideNav} />
				</ul>
			</div>
		</div>
	</div>
{/if}
