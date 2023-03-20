<script>
	import '../app.css';
	import Navbar from '$lib/components/Navbar.svelte';
	import Footer from '../lib/components/Footer.svelte';
</script>

<div class="grid gap-8 p-5 md:min-h-screen md:place-content-center">
	<nav>
		<Navbar />
	</nav>

	<main>
		<slot />
	</main>

	<footer class="mt-10 md:m-0">
		<Footer />
	</footer>
</div>
