<template>
	<section id="about_me" name="about_me">
		<div class="about_me_container">
			<div class="about_me_title">
				<h2>about me</h2>
				<h3>"프론트엔드 개발자를 꿈꾸는 저를 소개합니다."</h3>
			</div>
			<div class="about_me_info">
				<div class="about_me_text">
					<p>안녕하세요! 하고자 하는 일에 있어 도전하고 직접 경험해보며 성장하는 신입 프론트엔드 개발자 김동현입니다.
					제가 배운 기술들을 사용하여 무궁무진한 아이디어를 구현해 가는 과정이 흥미롭고 재밌습니다. 비록 구현해 나아가는 과정에서 힘든 상황이 있지만 개발의 근육이 붙어가는 과정이라고 생각합니다.
					지속적인 학습과 개인 발전을 통하여 빠르게 변화하는 시대와 트렌드에 도태되는 것이 아닌 더 멋진 내일이 올 수 있도록 발전하고 사용자들에게 있어서 가치 있는 웹 경험을 제공하는 것이 저의 목표입니다.
					저는 무엇이던지 끝가지 포기하지 않고 최선을 다해 도전한다면 결국 좋은 결과를 가져온다고 믿습니다.
					도전이 헛되지 않도록 배움에 있어 겸손한 자세로 꼼꼼하게 체크해 나아가는 프론트엔드 개발자가 되겠습니다. 감사합니다.</p>
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