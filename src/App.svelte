<script>
	import Header from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
	import Tabs from "./shared/Tabs.svelte";
	import CreatePollForm from "./components/CreatePollForm.svelte";

	let items = ['Current Polls', 'Add New Poll'];
	let activeItem = 'Current Polls';
	const handleTabChange = (e) => {
		activeItem = e.detail;
	}
</script>


<Header />
<main>
	<Tabs {activeItem} {items} on:tabChange={handleTabChange}/> 
	{#if activeItem=== 'Current Polls'}
		<p>Current Poll</p>
	{:else if activeItem === 'Add New Poll'}
		<p>Add New Poll</p>
	{/if}
</main>
<Footer />

<style>
	main {
		max-width: 960px;
		margin: 40px auto;

	}
	


</style>