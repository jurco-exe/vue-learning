<template>
	<div class="container mt-5">
		<div class="row">
			<div class="col">
				<div class="card bg-dark">
					<div class="card-body">
						<h5 class="card-title">{{ jobs[0].title }}</h5>
						<p class="card-text">{{ jobs[0].location }}</p>
						<p class="card-text">{{ jobs[0].salary }}</p>
						<p class="card-text">{{ jobs[0].id }}</p>
					</div>
				</div>
			</div>
			<div class="col">
				<div class="card bg-dark">
					<div class="card-body">
						<h5 class="card-title">{{ jobs[1].title }}</h5>
						<p class="card-text">{{ jobs[1].location }}</p>
						<p class="card-text">{{ jobs[1].salary }}</p>
						<p class="card-text">{{ jobs[1].id }}</p>
					</div>
				</div>
			</div>
			<div class="col">
				<div class="card bg-dark">
					<div class="card-body">
						<h5 class="card-title">{{ jobs[2].title }}</h5>
						<p class="card-text">{{ jobs[2].location }}</p>
						<p class="card-text">{{ jobs[2].salary }}</p>
						<p class="card-text">{{ jobs[2].id }}</p>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<!--! we are telling Vue that we are using TS  -->
<script lang="ts">
// defineComponent => is used to define the component,
// reactive => is used to create a reactive object,
// toRefs => is used to convert a reactive object to a plain object with reactive properties.
import { defineComponent, ref } from 'vue';
import Job from './types/Job';

export default defineComponent({
	name: 'App',
	components: {},
	setup() {
		const jobs = ref<Job[]>([
			{
				title: 'farm worker',
				location: 'lon lon ranch',
				salary: 30000,
				id: '1'
			},
			{
				title: 'quarryman',
				location: 'death mountain',
				salary: 40000,
				id: '2'
			},
			{
				title: 'flute player',
				location: 'the lost woods',
				salary: 35000,
				id: '3'
			},
			{
				title: 'fisherman',
				location: 'lake hylia',
				salary: 21000,
				id: '4'
			},
			{
				title: 'prison guard',
				location: 'gerudo walley',
				salary: 32000,
				id: '5'
			}
		]);

		return { jobs };
	}
});
</script>

<style lang="scss"></style>
