<template>
	<article class="text-center">
		<section class="m-8">
			<h2 class="text-2xl mb-8 lg:mb-16">Welcome to the User Directory</h2>
			<p class="m-4">
				This directory contains a paginated list of user data retrieved from the 
					<a 
						href="http://randomuser.me" 
						target="blank"
						class="text-blue-700 underline"
					>Random User Generator API</a>.
			</p>

			<p>
				Each page will have option to export the user data to a downloadable CSV file.
			</p>
		</section>

		<button 
			class="text-center mx-auto my-16 w-40 h-16"
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