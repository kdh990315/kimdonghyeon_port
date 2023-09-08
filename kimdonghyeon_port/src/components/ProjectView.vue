<template>
	<section id="project">
		<div class="project_container">
			<div class="project_title">
				<h3>project</h3>
				<div class="line"></div>
			</div>

			<div class="project_main">
				<article class="project_content" v-for="(port, index) in projectInfo" :key="index">
					<span>{{ index + 1 }}.</span>
					<div class="project_info">
						<img :src="port.src" />
						<p class="project_mainText">{{ port.mainText }}</p>
						<p class="project_subText">{{ port.subText }}</p>
						<div class="project_btn_box">
							<a :href="port.siteURL">site view</a>
							<a :href="port.codeURL">code view</a>
						</div>
					</div>
				</article>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	data() {
		return {
			projectInfo: [
				{
					src: "http://placehold.it/500X300",
					mainText: "main 더미텍스트입니다.",
					subText: "sub 더미 텍스트입니다. html 시멘틱태그를 이용하여 가장 기본적인 웹페이지를 만들었습니다.",
					siteURL: "#",
					codeURL: "#",
				},
				{
					src: "http://placehold.it/500X300",
					mainText: "main 더미텍스트입니다.",
					subText: "suv 더미텍스트입니다.",
					siteURL: "#",
					codeURL: "#",
				},
				{
					src: "http://placehold.it/500X300",
					mainText: "main 더미텍스트입니다.",
					subText: "suv 더미텍스트입니다.",
					siteURL: "#",
					codeURL: "#",
				},
				{
					src: "http://placehold.it/500X300",
					mainText: "main 더미텍스트입니다.",
					subText: "suv 더미텍스트입니다.",
					siteURL: "#",
					codeURL: "#",
				},
			],
		}
	}
}
</script>

<style lang="scss" scoped>
@import '@/scss/mixin.scss';

.project_container {
	max-width: 80%;
	margin: 0 auto 0 15%;
	margin-top: 300px;

	.project_title {
		position: sticky;
		top: 130px;
		padding-bottom: 25px;

		h3 {
			@include title-text;
		}

		.line {
			width: 35%;
			height: 2px;
			background-color: #fff;
			border-radius: 50%;
		}
	}
	
	.project_main {
		.project_content {
			width: 100%;
			padding-bottom: 50px;
			position: sticky;


			span {
				font-size: 5vw;
				font-weight: 900;
				padding-left: 30px;
			}

			.project_info {
				position: sticky;
				
				@include c-center;

				img {
					margin-bottom: 20px;
				}

				p {
					color: black;
				}

				.project_mainText {
					font-size: 1.5rem;
					font-weight: 900;
					padding: 5px 0;
				}

				.project_subText {
					font-size: 1rem;
					text-align: center;
					padding-top: 5px;
				}

				.project_btn_box {
					width: 300px;
					margin-top: 50px;

					@include center-sb;

					a {
						display: block;
						font-size: 1.2rem;
						color: black;
						padding: 8px 15px;
						background-color: #ccc;
					}
				}
			}

			&:nth-of-type(1) {
				background-color: #ffe4c4;
				top: 255px;

				@media (max-width: 800px) {
					top: 193px;
				}
			}
			&:nth-of-type(2) {
				background-color: #e7ceb0;
				top: 275px;

				@media (max-width: 800px) {
					top: 213px;
				}
			}
			&:nth-of-type(3) {
				background-color: #c5b095;
				top: 295px;
				
				@media (max-width: 800px) {
					top: 233px;
				}
			}
			&:nth-of-type(4) {
				background-color: #8f806e;
				top: 315px;
				
				@media (max-width: 800px) {
					top: 253px;
				}
			}
		}
	}

	@media (max-width: 800px) {
		width: 100%;
		margin: 150px auto 0 auto;
	}
}
</style>