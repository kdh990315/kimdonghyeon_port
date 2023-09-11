<template>
	<section id="about_me" name="about_me">
		<div class="about_me_container">
			<div class="about_me_title">
				<h2>about me</h2>
				<h3>"프론트엔드 개발자를 꿈꾸는 저를 소개합니다."</h3>
			</div>
			<div class="about_me_info">
				<div class="about_me_text">
					<p>더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.</p>
					<p>더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.</p>
					<p>더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.</p>
					<p>더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.더미 텍스트입니다.</p>
				</div>
				<div class="about_me_portrait">
					<img src="@/assets/images/portrait.jpg" alt="증명사진">
				</div>
			</div>
		</div>
		<div class="skill_wrap">
			<div class="skill_title">
				<h3>skills</h3>
			</div>
			<div class="skill_container">
				<!-- html -->
				<div class="chart" v-for="(chart, index) in chartData" :key="index">
					<div class="charts">
						<svg>
							<circle cx="110" cy="110" r="100"></circle>
						</svg>
						<p :data-num="chart.data">0</p>
					</div>

					<span>{{ chart.title }}</span>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	data() {
		return {
			chartData: [
				{ title: 'HTML', data: 90 },
				{ title: 'CSS/SCSS', data: 90 },
				{ title: 'JACASCRIPT', data: 80 },
				{ title: 'VUE.JS', data: 65 },
			],

			//skill scroll trigger
			isScrollEctive: false,
			currentScrollPos: 0, //현재 스크롤의 양
			skillScrollPos: 0, //skill_wrap의 스크롤 위치
		}
	},
	methods: {
		scrollTrigger() {
			if (this.currentScrollPos > this.skillScrollPos - 500) {
				this.isScrollEctive = true;
				this.numAnimation();
				this.svgAnimation();
			}
		},
		numAnimation() {
			let chart = document.querySelectorAll('.charts > p');

			const aa = (index) => {
				let chartData = chart[index].getAttribute('data-num'),
					count = 0,
					timer = setInterval(() => {
						++count;
						chart[index].innerText = count;
						if(count == chartData) clearInterval(timer)
					}, 20);
			}

			for(let i = 0; i < chart.length; i++) {
				aa(i);
			}
		},
		svgAnimation() {
			
			let chart = document.querySelectorAll('.charts > p'),
				circle = document.querySelectorAll('circle');

			chart.forEach((item,index) => {
				let chartdata = item.getAttribute('data-num');

				circle[index].style.strokeDashoffset = Math.floor(628 - (628 * chartdata / 100));
			});
		}
	},
	mounted() {
		let EvTarget = document.querySelector('.skill_wrap'),
			docEl = document.documentElement;

		document.addEventListener('scroll', () => {
			this.skillScrollPos = EvTarget.offsetTop;
			this.currentScrollPos = docEl.scrollTop;
			
			if(!this.isScrollEctive) {
				this.scrollTrigger();
			}
		});
	}
}
</script>

<style lang="scss" scoped>
@import '@/scss/mixin.scss';

@import '@/scss/AboutMeView.scss';
</style>