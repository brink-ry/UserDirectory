<template>
	<article>
		<h1>User Directory</h1>

		<section>
			<h2>Welcome to the user directory.</h2>
			<p>
				This directory will display a paginated list of user data retrieved from the <a href="http://randomuser.me" target="blank">Random User Generator API</a>.
			</p>

			<p>
				You will be able to navigate through the user data.
			</p>

			<p>
				Each page will have option to export the user data to a downloadable CSV file.
			</p>
		</section>
	</article>
</template>

<script>
export default {
	name: 'Home'
}
</script>