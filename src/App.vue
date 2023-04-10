<template>
	<div class="container text-center mt-5">
		<h1>{{ name }} {{ age }}</h1>
		<button @click="changeName('Jano')">Change Name</button>
		<button @click="changeAge(30)">Change Age</button>
	</div>
</template>

<!--! we are telling Vue that we are using TS  -->
<script lang="ts">
import { defineComponent } from 'vue';

// we cannot use this type of writing types in our Component:
// let age: number | string = 25;

// this is way how we make the Component
export default defineComponent({
	name: 'App',
	components: {},
	// now we add a lit a bit of DATA
	// this data func. will return object of data
	data() {
		return {
			name: 'Juraj',

			// so we use it like this
			age: 25 as number | string
		};
	},
	// if we want to change the calue at some point we need will use METHOD property
	// and inside this property we will make function to actualy change the value
	methods: {
		changeName(name: string) {
			this.name = name;
		},

		changeAge(age: string | number) {
			this.age = age;
		}
	}
});
</script>

<style lang="scss"></style>
