<template>
	<section id="script">
		<div class="script_container">
			<div class="script_title">
				<h3>script</h3>
				<p>작업물</p>
				<div class="script_line"></div>
			</div>
			<div class="script_contents">
				<div class="contents" v-for="(content, index) in scrpitContents" :key="index">
					<div class="contents_left">
						<img src="http://placehold.it/700X400" />
					</div>
					<div class="contents_right">
						<p class="num">{{ index + 1 }}.</p>
						<div class="line"></div>
						<h4>{{ content.title }}</h4>
						<p>{{ content.subText }}</p>
						<div class="contents_btn_box">
							<base-button :href="content.siteView">site view</base-button>
							<base-button :href="content.codeView">code view</base-button>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
	mounted: function () {
		this.scrollAnimation();

	},
	data() {
		return {
			scrpitContents: [
				{
					img: "#",
					title: "title dummy text",
					subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
					siteView: "#",
					codeView: "#",
				},
				{
					img: "#",
					title: "title dummy text",
					subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
					siteView: "#",
					codeView: "#",
				},
				{
					img: "#",
					title: "title dummy text",
					subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
					siteView: "#",
					codeView: "#",
				},
				{
					img: "#",
					title: "title dummy text",
					subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
					siteView: "#",
					codeView: "#",
				},
				{
					img: "#",
					title: "title dummy text",
					subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
					siteView: "#",
					codeView: "#",
				},
				{
					img: "#",
					title: "title dummy text",
					subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
					siteView: "#",
					codeView: "#",
				},
				{
					img: "#",
					title: "title dummy text",
					subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
					siteView: "#",
					codeView: "#",
				},
				{
					img: "#",
					title: "title dummy text",
					subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
					siteView: "#",
					codeView: "#",
				},
				{
					img: "#",
					title: "title dummy text",
					subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
					siteView: "#",
					codeView: "#",
				},
				{
					img: "#",
					title: "title dummy text",
					subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
					siteView: "#",
					codeView: "#",
				},
			]
		}
	},

	methods: {
		scrollAnimation() {
			const contents = gsap.utils.toArray(".contents");

			// gsap.to(contents, {
			// 	xPercent: -125 * (contents.length - 1),
			//     ease: "none",
			//     scrollTrigger: {
			//         trigger: "#script",
			//         start: "top 130px",
			//         end: "+=9000",
			//         pin: true,
			//         scrub: 1,
			//         markers: false,
			//         invalidateOnRefresh: true,
			//         anticipatePin: 1,
			//     }
			// });
			ScrollTrigger.matchMedia({
				"(min-width: 800px)": function () {
					gsap.to(contents, {
						xPercent: -125 * (contents.length - 1),
						ease: "none",
						scrollTrigger: {
							trigger: "#script",
							start: "top 130px",
							end: "+=9000",
							pin: true,
							scrub: 1,
							markers: false,
							invalidateOnRefresh: true,
							anticipatePin: 1,
						}
					});
				},
				"(max-width: 799px)": function () {
					gsap.to(contents, {
						xPercent: -145 * (contents.length - 1),
						ease: "none",
						scrollTrigger: {
							trigger: "#script",
							start: "top 130px",
							end: "+=12000",
							pin: true,
							scrub: 1,
							markers: false,
							invalidateOnRefresh: true,
							anticipatePin: 1,
						}
					});
				},
			})
		}
	}
}
</script>

<style lang="scss" scoped>
@import '@/scss/mixin.scss';

#script {
	width: 100%;
	height: 30vh;
	margin-top: 300px;

	.script_container {
		max-width: 80%;
		margin: 0 auto 0 15%;

		.script_title {
			color: #fff;
			width: 100%;

			h3 {
				font-size: 5vw;
				font-weight: bold;
				text-transform: uppercase;
				display: inline-block;
				font-family: 'Poppins', sans-serif;
			}

			p {
				font-size: 1vw;
				font-weight: 400;
				display: inline-block;
				margin-left: 20px;
			}

			.script_line {
				width: 55%;
				height: 2px;
				background-color: #fff;
				border-radius: 50%;
			}
		}

		.script_contents {
			width: 16080px;
			display: flex;
			flex-wrap: wrap;
			z-index: 10;

			.contents {
				@include center-se;
				width: 1500px;
				background-color: beige;
				margin: 30px 120px 0 0;

				&:last-child {
					margin: 30px 0 0 0;
				}



				.contents_left {
					width: 50%;
					padding: 30px 0;
					@include center;

					img {
						border-radius: 50px;
					}
				}

				.contents_right {
					width: 40%;

					.num {
						font-size: 3vw;
						font-weight: 900;
					}

					.line {
						width: 100%;
						height: 5px;
						background-color: #fff;
						margin-bottom: 20px;
					}

					h4 {
						font-size: 3vw;
						font-weight: 600;
						font-family: 'Poppins', sans-serif;
						margin-bottom: 30px;
					}

					p {
						font-size: 1rem;
						font-weight: 400;
						line-height: 1.8;
					}

					.contents_btn_box {
						width: 300px;
						margin: 50px auto 0 auto;

						@include center-sb;
					}
				}
			}
		}
	}

	@media (max-width: 800px) {

		.script_container {
			margin: 0 auto;

			.script_contents {

				.contents {
					width: 500px;
					text-align: center;
					padding-bottom: 30px;
					border-radius: 20px;
					@include c-center;

					.contents_left {

						img {
							width: 400px;
						}
					}

					.contents_right {
						width: 100%;

						.num {
							font-size: 2.5rem;
						}

						h4 {
							font-size: 2.5rem;
						}

						.line {
							width: 65%;
							margin: 0 auto 30px auto;
						}

						.contents_btn_box {
							margin: 0 auto;
						}
					}
				}

			}
		}


	}
}
</style>