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
import { defineComponent, ref } from 'vue';

export default defineComponent({
	name: 'App',

	// The components property is used to declare child components of this component. In this example, there are no child components.
	components: {},

	// The setup() function is a special function in Vue.js that allows you to set up the reactive data/Refs and functions for the component. It returns an object containing reactive properties.
	setup() {
		// The ref() function creates a reference to a value that can be reactive. In this case, name is a reference to the string value "Juraj" and age is a reference to the number value 25.
		const name = ref('Juraj');
		const age = ref<number | string>(25);

		// The age.value and name.value lines update the values of age and name, respectively. The .value syntax is used to access the value of the reference.
		age.value = 10;
		name.value = 'Linda';

		// The return { name, age } line returns an object containing the name and age references.
		return { name, age };
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
