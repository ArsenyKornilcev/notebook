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
	<keep-alive>
		<component :is="selectedTab"></component>
	</keep-alive>
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
			addNote(title, description, url) {
				const date = new Date();
				const newNote = {
					id: date.toISOString(),
					title: title,
					description: description,
					url: url,
				};
				this.storedResources.unshift(newNote);
				this.selectedTab = "stored-resource";
			},
		},
		computed: {
			storedResBtnMode() {
				return this.selectedTab === "stored-resource" ? null : "flat";
			},
			addResBtnMode() {
				return this.selectedTab === "add-resource" ? null : "flat";
			},
		},
		provide() {
			return {
				resources: this.storedResources,
				addNote: this.addNote,
			};
		},
	};
</script>

<style></style>
