<script>
	import ContentContainer from '$lib/components/ContentContainer.svelte';
	import MainContent from '$lib/components/Contents/MainContent.svelte';
	import NewContent from '$lib/components/Contents/NewContent.svelte';
	import FootContent from '$lib/components/Contents/FootContent.svelte';
</script>

<ContentContainer>
	<MainContent slot="mainContent" />
	<NewContent slot="newContent" />
	<FootContent slot="footContent" />
</ContentContainer>
