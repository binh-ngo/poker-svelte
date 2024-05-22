<!-- Layout for All Pages -->
<script>
	import '../app.css'
	import Header from './Header.svelte';
</script>
<div>
	<Header></Header>

	<main>
		<slot></slot>
	</main>


</div>

