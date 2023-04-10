<template>
	<div class="container text-center mt-5">
		<h1>{{ name }} {{ age }}</h1>
		<button @click="changeName('Jano')">Change Name</button>
		<button @click="changeAge(30)">Change Age</button>
	</div>
</template>

<!--! we are telling Vue that we are using TS  -->
<script lang="ts">
// defineComponent => is used to define the component,
// reactive => is used to create a reactive object,
// toRefs => is used to convert a reactive object to a plain object with reactive properties.
import { defineComponent, reactive, toRefs } from 'vue';

export default defineComponent({
	name: 'App',

	// The components property is used to declare child components of this component. In this example, there are no child components.
	components: {},

	// The setup() function is a special function in Vue.js that allows you to set up the reactive data and functions for the component. It returns an object containing reactive properties.
	setup() {
		// The reactive() function creates a reactive object that will be used to store the component's data.
		// The state object contains two properties, name and age, both of which are reactive.
		const state = reactive({
			name: 'Juraj',
			age: 25 as string | number
		});

		state.name = 'Jurco';

		// The toRefs() function is used to convert the reactive state object to a plain object with reactive properties. This allows us to use the state properties in the template section.
		return { ...toRefs(state) };
	},

	// The methods object contains two functions, changeName() and changeAge(), which are used to change the name and age properties of the state object.
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
