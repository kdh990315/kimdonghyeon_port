<template>
	<section id="intro">
		<div class="intro_wrap">
			<div class="intro_text_container">
				<div class="intro_title">
					<strong>welcome to my</strong>
					<h1>portfolio</h1>
				</div>
				<div class="intro_text">
					<p>안녕하세요. 저의 포트폴리오에 오신 것을 환영합니다.</p>
					<p>프론트엔드 개발자를 꿈꾸며 준비한 결과물들을 보기 쉽게 정리해 놓았습니다.</p>
					<p>비록 부족한 부분이 있겠지만 편안하게 보시며 즐겨주시면 감사하겠습니다.</p>
				</div>
			</div>
		</div>
	</section>
</template>

<style lang="scss" scoped>
@import '@/scss/mixin.scss';

#intro {
	height: 100vh;

	.intro_wrap {
		max-width: 80%;
		height: 100%;
		margin: 0 auto 0 15%;

		.intro_text_container {
			width: 100%;
			margin-top: 400px;

			.intro_title {
				font-family: 'Poppins', sans-serif;

				strong {
					font-size: 7vw;
					font-weight: bold;
					text-transform: uppercase;
				}

				h1 {
					font-size: 4vw;
					font-weight: 300;
					text-transform: capitalize;
				}
			}

			.intro_text {
				margin-top: 25px;

				p {
					line-height: 1.5;
					font-family: 'Noto Sans KR', sans-serif;
				}
			}

			@media (max-width: 800px) {
				@include position-center;

				width: 100%;
				margin: 0;
				text-align: center;

				.intro_title {
					font-family: 'Poppins', sans-serif;


					h1 {
						font-weight: 200;
						font-size: 5vw;
					}
				}
			}
		}
	}
}
</style>