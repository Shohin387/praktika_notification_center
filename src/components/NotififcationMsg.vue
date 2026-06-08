<script setup>
import { ref } from 'vue';

const hidden = ref(false)
const props = defineProps({
	type: {
		type: String,
		default: 'success',
	},
	header: {
		type: String,
		default: 'Ok!',
	}
})

</script>

<template>
	<div :class="type + ' cntNotif'" v-if="!hidden">
		<div>
			<h2 class="header">{{ header }}</h2>
			<p><slot></slot></p>
		</div>	
		
		<img @click="() => hidden = !hidden" class="close" width="15px" src="../assets/close-red.png" v-if="type === 'error'" alt="">
		<img @click="() => hidden = !hidden" class="close" width="15px" src="../assets/close.png" v-else alt="">
	</div>
	

</template>

<style scoped>
.cntNotif {
	display: grid;
	padding-inline: 20px;
	padding-block: 13px;
	width: 400px;
	border-radius:6px ;
	margin: auto;
	margin-bottom: 25px;

	grid-template-columns: auto 12px;
}

.header {
	margin-bottom: 5px;
}

.error {
	border: 1px solid rgb(202, 0, 0);
	color: rgb(173, 0, 0);
	background-color: rgba(255, 82, 82, 0.171);
}

.success {
	border: 1px solid rgb(0, 172, 43);
	color: rgb(0, 152, 0);
	background-color: rgba(143, 255, 82, 0.171);
}

.close {
	cursor: pointer;
	width: 12px;
}
</style>