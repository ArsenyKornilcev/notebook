<template>
	<base-card>
		<form action="">
			<div class="form-control">
				<label for="title">Title</label>
				<input
					type="text"
					id="title"
					name="title" />
			</div>
			<div class="form-control">
				<label for="description">Title</label>
				<textarea
					name="description"
					id="description"
					rows="3"></textarea>
			</div>
		</form>
		<div>
			<base-button type="submit">Add Resources</base-button>
		</div>
	</base-card>
</template>
<script>
	export default {
		name: "AddResource",
	};
</script>
<style scoped>
	label {
		font-weight: bold;
		display: block;
		margin-bottom: 0.5rem;
	}

	input,
	textarea {
		display: block;
		width: 100%;
		font: inherit;
		padding: 0.15rem;
		border: 1px solid #ccc;
	}

	input:focus,
	textarea:focus {
		outline: none;
		border-color: #3a0061;
		background-color: #f7ebff;
	}

	.form-control {
		margin: 1rem 0;
	}
</style>
