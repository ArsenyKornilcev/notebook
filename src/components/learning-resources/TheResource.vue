<template>
	<base-card>
		<base-button
			:mode="storedResBtnMode"
			@click="selectTab('stored-resource')"
			>Stored Notes</base-button
		>
		<base-button
			:mode="addResBtnMode"
			@click="selectTab('add-resource')"
			>Add Notes</base-button
		>
	</base-card>
	<component :is="selectedTab"></component>
</template>

<script>
	import StoredResource from "./StoredResource.vue";
	import AddResource from "./AddResource.vue";

	export default {
		name: "TheResource",
		components: {
			StoredResource,
			AddResource,
		},
		data() {
			return {
				selectedTab: "stored-resource",
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
		methods: {
			selectTab(tab) {
				this.selectedTab = tab;
			},
		},
		computed: {
			storedResBtnMode() {
				return this.selectedTab === "stored-resource" ? null : "flat";
			},
			addResBtnMode() {
				return this.selectedTab === "add-resource" ? null : "flat";
			}
		},
		provide() {
			return {
				resources: this.storedResources,
			};
		},
	};
</script>

<style></style>
