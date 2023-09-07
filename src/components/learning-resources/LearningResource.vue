<template>
	<li>
		<base-card>
			<div>
				<header>
					<h3>{{ title }}</h3>
					<base-button mode="flat" @click="removeNote(id)">Delete</base-button>
				</header>
			</div>
			<p>{{ description }}</p>
			<nav>
				<a :href="link">Link</a>
			</nav>
		</base-card>
	</li>
</template>
<script>
	export default {
		name: "LearningResource",
		props: ["id", "title", "description", "link"],
		inject: ["removeNote"],
	};
</script>
<style scoped>
	li {
		margin: auto;
		max-width: 40rem;
		list-style: none;
	}

	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	h3 {
		font-size: 1.25rem;
		margin: 0.5rem 0;
	}

	p {
		margin: 0.5rem 0;
	}

	a {
		text-decoration: none;
		color: #ce5c00;
	}
</style>
