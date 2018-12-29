<template>
<div class="notes">
	<article
		class="message"
		v-for="note in notes"
		>
		<div class="message-header">
			{{ note.title }}
			<button class="delete" aria-label="delete"></button>
		</div>
		<div class="message-body">
			{{ note.body }}
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