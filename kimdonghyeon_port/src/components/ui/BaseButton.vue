<template>
	<a :href="href" target="_blank">
		<slot></slot>
	</a>
</template>

<script>
export default {
	props: ['href'],

}
</script>

<style lang="scss" scoped>
a {
	display: block;
	font-size: 1.2rem;
	color: black;
	padding: 8px 15px;
	background-color: #ccc;
}
</style>