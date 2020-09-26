<template>
	<article class="text-center">
		<h2 class="text-xl">Welcome to the user directory.</h2>
		<p>
			This directory will display a paginated list of user data retrieved from the <a href="http://randomuser.me" target="blank">Random User Generator API</a>.
		</p>

		<p>
			You will be able to navigate through the user data.
		</p>

		<p>
			Each page will have option to export the user data to a downloadable CSV file.
		</p>

		<button 
			class="text-center mx-auto"
			@click="clickResultsRoute"
		>
			<router-link id="viewResults" :to="{ name: 'Results' }">View Directory</router-link>
		</button>
	</article>
</template>

<script>
export default {
	name: 'Home',
	methods: {
		clickResultsRoute () {
			const anchorTarget = document.getElementById('viewResults');
			anchorTarget.click();
		}
	}
}
</script>