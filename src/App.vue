<template>
	<the-header headerCaption="Notebook"></the-header>
	<the-resource></the-resource>
</template>

<script>
	import TheHeader from "@/components/layouts/TheHeader";
	import TheResource from "./components/learning-resources/TheResource.vue";

	export default {
		name: "App",
		components: {
			TheHeader,
			TheResource
		},
		data() {
			return {
				
			};
		},
	};
</script>

<style>
	html {
		font-family: sans-serif;
	}
	body {
		margin: 0;
	}
</style>
