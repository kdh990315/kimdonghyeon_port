<template>
	<section id="project">
		<div class="project_container">
			<div class="project_title">
				<h3>project</h3>
				<p>나의 결과물</p>
				<div class="line"></div>
			</div>
		</div>
	</section>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import '@/scss/mixin.scss';

.project_container {
	max-width: 80%;
	margin: 0 auto 0 15%;
	margin-top: 300px;

	.project_title {

		h3 {
			@include title-text;
		}

		p {
			font-size: 2vw;
			padding: 1rem 0;
		}

		.line {
			width: 300px;
			height: 2px;
			background-color: #fff;
			border-radius: 50%;
		}
	}
}
</style>