<template>
<form v-on:submit.prevent="$emit('new-note',submittedNote)">
	<div class="field is-horizontal">
		<label for="titleField" class="label">Title</label>
		<div class="control"><input type="text" id="titleField" v-model="title"></div>
	</div>
	<div class="field is-horizontal">
		<label for="noteField" class="label">Note</label>
		<div class="control"><textarea class="textarea" id="noteField" v-model="body"></textarea></div>
	</div>
	<div class="field is-grouped is-horizontal">
		<div class="control"><button type="submit" class="button is-link">Add Note</button></div>
		<div class="control"><button type="reset" class="button is-text">Reset</button></div>
	</div>
</form>
</template>

<script>
export default {
	name: "NoteForm",
	data: () => {
		return {
			body: "",
			title: ""
		}
	},
	computed: {
		submittedNote: function() {
			return {
				title: this.title,
				body: this.body
			}
		}
	}
}
</script>

<style scoped>

</style>