<template>
		<v-container class="d-flex justify-space-between mx-2">
			<beat-element
				v-for="(beat, beatIndex) in metronomeObject.accents"
				:key="beatIndex"
				:metronomeIndex="index"
				:beatIndex="beatIndex"
			/>
		</v-container>
</template>
<script>
import BeatElement from "@/components/BeatElement.vue";

export default {
	name: "beat-container",
	computed: {
		metronomeObject: function() {
			return this.$store.state.metronome[this.index];
		}
	},
	props: ["index"],
	components: {
		BeatElement
	}
};
</script>
<style scoped></style>
