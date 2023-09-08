<template>
	<section id="footer">
		<span>2023 @ Kim Dong Hyeon Portfolio</span>
	</section>
</template>

<style lang="scss" scoped>
@import '@/scss/mixin.scss';

#footer {
	width: 100%;
	height: 30px;
	font-size: 12px;
	margin-bottom: 30px;
	border-top: 1px solid #ccc;
	backdrop-filter: blur(5px);
	border-bottom: 1px solid #ccc;
	@include center;

	span {
		color: #ccc;
	}
}
</style>