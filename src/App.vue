<template>
	<stored-resource :resources="storedResources"></stored-resource>
</template>

<script>
	import StoredResource from './components/learning-resources/StoredResource.vue';

	export default {
		name: "App",
		components: {
			StoredResource,
		},
		data() {
			return {
				storedResources: [
					{
						id: "official-gide",
						title: "Official gide",
						description: "The official Vue.js documentation",
						url: "https://v3.ru.vuejs.org/ru",
					},
					{
						id: "google",
						title: "Google",
						description: "Learn to Google",
						url: "https://google.com",
					},
				],
			};
		},
	};
</script>

<style></style>
