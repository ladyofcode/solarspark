<script lang="ts">
	import '../app.css';
	import Footer from '$lib/Footer.svelte';
	import MainMenu from "$lib/MainMenu.svelte";
</script>

<MainMenu></MainMenu>

<slot></slot>

<Footer></Footer>