<template>
	<ul>
		<learning-resource
			v-for="resource in resources"
			:key="resource"
			:title="resource.title"
			:description="resource.description"
			:link="resource.url">
		</learning-resource>
	</ul>
</template>
<script>
	import LearningResource from "./LearningResource.vue";

	export default {
		name: "StoredResource",
		components: {
			LearningResource,
		},
		props: ["resources"],
	};
</script>
<style></style>
