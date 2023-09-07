<template>
	<base-dialog @close="confirmError"
		v-if="inputIsInvalid"
		title="Invalid input">
		<template #default>
			<p>Unfortunately, your input is invalid.</p>
			<p>Please check all inputs and make sure you enter at least one character into each input field.</p>
		</template>
		<template #actions>
			<base-button @click="confirmError">
				Okey
			</base-button>
		</template>
	</base-dialog>

	<base-card>
		<form @submit.prevent="submitData">
			<div class="form-control">
				<label for="title">Title</label>
				<input
					type="text"
					id="title"
					name="title"
					ref="titleInput" />
			</div>
			<div class="form-control">
				<label for="description">Title</label>
				<textarea
					name="description"
					id="description"
					rows="3"
					ref="descriptionInput"></textarea>
			</div>
			<div class="form-control">
				<label for="link"> Link </label>
				<input
					id="link"
					name="link"
					type="url"
					ref="urlInput" />
			</div>
			<div>
				<base-button type="submit">Add Resources</base-button>
			</div>
		</form>
	</base-card>
</template>
<script>
	export default {
		name: "AddResource",
		inject: ["addNote"],
		data() {
			return {
				inputIsInvalid: false,
			};
		},
		methods: {
			submitData() {
				const enteredTitle = this.$refs.titleInput.value.trim();
				const enteredDescription =
					this.$refs.descriptionInput.value.trim();
				const enteredUrl = this.$refs.urlInput.value.trim();

				if (
					enteredTitle === "" ||
					enteredDescription === "" ||
					enteredUrl === ""
				) {
					this.inputIsInvalid = true;
					return;
				}
				this.addNote(enteredTitle, enteredDescription, enteredUrl);

				this.$refs.titleInput.value = "";
				this.$refs.descriptionInput.value = "";
				this.$refs.urlInput.value = "";
			},
			confirmError() {
				this.inputIsInvalid = false;
			},
		},
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
