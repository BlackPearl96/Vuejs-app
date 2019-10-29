<template>
  <div class="component">
    <h3>User Details</h3>
    <p>Tuoi toi: {{ age }}</p>
		<button v-on:click="changeAge">Doi tuoi</button>
  </div>
</template>

<script>
import { eventBus } from 'main'
export default {
	props: ["age"],
	data: function (){
		return{ bla: this.age };
	},
	created () {
		eventBus.$on('ageWasEdited', (age) => {
			this.age = age
		})
	},
	methods:{
		changeAge: function (){
			this.bla = 30
			this.$emit('ageWasUpdated', this.bla)
		}
	}
};
</script>
