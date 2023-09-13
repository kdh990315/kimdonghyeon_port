<template>
	<section id="footer">
		<div class="footer_container">
			<div class="footer_wrap" :class="{ective: footerisvisible}">
				<div class="footer_left">
					<strong>thank you<br>for<br>watching</strong>

					<p>끝까지 봐주셔서 감사합니다 :)</p>
				</div>
				<div class="footer_right">
					<ul>
						<li class="info_contents" v-for="(info, index) in info" :key="index">
							<span>{{ info.question }}</span><em>{{ info.answer }}</em>
						</li>
					</ul>
				</div>
			</div>
		</div>

		<footer>
			<span>2023 @ Kim Dong Hyeon Protfolio</span>
		</footer>
	</section>
</template>

<script>
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
	data() {
		return {
			info: [
				{ question: "name", answer: "김동현" },
				{ question: "birthday", answer: "1999 . 03 . 15" },
				{ question: "home", answer: "경기도 시흥시 장곡동" },
				{ question: "education", answer: "용인송담대학교 정보통신과 졸업" },
				{ question: "hobby", answer: "낚시🎣  조깅🏃" },
				{ question: "mbti", answer: "ESTP" },
			],
			footerisvisible: false,

		}
	},
	mounted: function () {
		this.scrollAnimation();
	},
	methods: {
		scrollAnimation() {
			let footer_box = document.querySelector('.footer_wrap');

			gsap.to(footer_box, {
				scrollTrigger: {
					trigger: footer_box,
					start: "top 50%",
					end: "bottom 50%",
					scrub: 1,
					markers: false,
					onToggle: (self) => {
						self.isActive ? this.footerisvisible = true : this.footerisvisible = false;
						console.log(self.isActive)
					}
				},
			});
		}
	}
}
</script>

<style lang="scss" scoped>
@import '@/scss/mixin.scss';

.footer_container {
	max-width: 80%;
	height: 80vh;
	margin: 250px auto 0 15%;

	.footer_wrap {
		margin: 0 auto;
		padding: 8vw 30px;
		// background-color: yellowgreen;
		opacity: 0;
		transition: opacity .5s;
		@include center-sb;



		&.ective {
			opacity: 1;

			.footer_left {
				opacity: 1;
				transform: translateX(0px);
			}

			.footer_right {
				opacity: 1;
				transform: translateX(0px);
			}
		}

		.footer_left {
			width: 50%;
			opacity: 0;
			position: relative;
			transform: translateX(-35px);
			transition: all 1.5s 1.5s;

			strong {
				text-transform: capitalize;
				font-size: 5vw;
				font-weight: bold;
				font-family: 'Poppins', sans-serif;
				line-height: 1.2;
			}

			p {
				font-size: 1vw;
				font-weight: 400;
				letter-spacing: 3.2px;
				font-family: "Be Vietnam Pro", sans-serif;
				padding-top: 15px;
			}
		}

		.footer_right {
			width: 50%;			
			opacity: 0;
			position: relative;
			transform: translateX(-35px);
			transition: all 1.5s 2s;

			ul {

				li {
					padding: 10px 0;
					border-top: 1px solid #ccc;
					font-family: 'Poppins', sans-serif;
					padding-left: 10px;

					&:first-child {
						border-top: none;
					}


					span {
						text-transform: uppercase;
						font-size: 1.5vw;
						letter-spacing: 1.2px;
					}

					em {
						margin-left: 40px;
						font-size: 1vw;
						opacity: 0;
						transition: opacity .3s;
					}

					&:hover {
						em {
							opacity: 1;
						}
					}
				}
			}
		}
	}

	@media (max-width: 800px) {
		margin: 0 auto;		

		.footer_wrap {
			@include c-center;
			padding: 12vw 0;

			.footer_left {
				width: 80%;

				strong {
					font-size: 3rem;
				}

				p {
					font-size: 1rem;
				}
			}

			.footer_right {
				margin-top: 40px;
				width: 80%;

				ul {
					li {
						span {
							font-size: 0.9rem;
						}

						em {
							font-size: 0.7rem;
						}
					}
				}
			}
		}
	}
}

footer {
	width: 100%;
	height: 30px;
	position: relative;
	bottom: 5%;
	border-top: 1px solid #ccc;
	border-bottom: 1px solid #ccc;

	@include center;

	span {
		letter-spacing: 1.2px;
		font-size: 12px;
	}
}
</style>