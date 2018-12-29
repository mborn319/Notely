<template>
<div class="notes">
	<article
		class="message"
		v-for="note in notes"
		>
		<div class="message-header">
			{{ note.title }}
			<button class="delete" aria-label="delete" v-on:click.prevent="$emit('delete-note',note)"></button>
		</div>
		<div class="message-body">
			{{ note.body }} <button class="button is-text is-pulled-right" v-on:click="$emit('edit-note',note)">Edit</button>
		</div>
	</article>
</div>
</template>

<script>
export default {
	name: "NoteList",
	props: {
		notes: Array
	}
}
</script>

<style scoped>

</style>