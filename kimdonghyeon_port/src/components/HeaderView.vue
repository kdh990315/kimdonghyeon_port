<template>
	<section id="header">
		<header>
			<div class="logo_box">
				<div class="logo"></div>
			</div>
			<nav>
				<ul>
					<li v-for="(menu, index) in headerMenu" :key="index">
						<a :href="menu.url" @click="HeaderAnchor($event)">
							<span>.0{{ index + 1 }}</span>{{ menu.menu }}
						</a>
					</li>
				</ul>
			</nav>

			<div class="header_mobile_nav" @click="HeaderMobileEvent" :class="{ show: isvisible }">
				<span></span>
			</div>

			<div class="header_moblie" :class="{ show: isvisible }">
				<ul>
					<li v-for="(menu, index) in headerMenu" :key="index" class="mobil_menu">
						<a :href="menu.url" @click="HeaderAnchor($event)">{{ menu.menu }}</a>
					</li>
					<li class="mobil_menu">
						<a :href="icon.href" v-for="(icon, index) in icons" :key="index">
							<i :class="icon.iconName"></i>
						</a>
					</li>
				</ul>
			</div>

		</header>
		<aside>
			<div class="icon_box">
				<div v-for="(icon, index) in icons" :key="index">
					<i :class="icon.iconName"></i>
					<div class="icon_sub">
						<a :href="icon.href">{{ icon.text }}</a>
					</div>
				</div>

			</div>
		</aside>
	</section>
</template>

<script>
import gsap from "gsap";

export default {
	data() {
		return {
			headerMenu: [
				{ menu: 'intro', url: '#intro' },
				{ menu: 'about me', url: '#about_me' },
				{ menu: 'project', url: '#project' },
				{ menu: 'script', url: '#script' },
				{ menu: 'footer', url: '#footer' },
			],
			icons: [
				{ href: 'https://instagram.com/dd_dodd_odo?igshid=MzRlODBiNWFlZA==', iconName: "fa-brands fa-square-instagram", text: '인스타그램 바로 가기' },
				{ href: 'https://blog.naver.com/dh_dv_note', iconName: "fa-brands fa-blogger", text: '개인 블로그 바로가기'  },
				{ href: '#', iconName: "fa-solid fa-square-envelope", text: 'kdh990315@naver.com'},
				{ href: '#', iconName: "fa-solid fa-square-phone", text: '010 - 5509 - 3095'},
			],

			isvisible: false,

		}
	},
	methods: {
		HeaderMobileEvent() {
			this.isvisible = !this.isvisible;

			let mobil_menu = document.querySelectorAll('.mobil_menu');

			if(this.isvisible) {
				gsap.to(mobil_menu, {
					xPercent: 120,
					duration: .9,
					stagger: 0.2,
					ease: "elastic.out(1, 0.3)"
				});
			} else {
				gsap.to(mobil_menu, {
					xPercent: -120,
				})
			}
		},
		HeaderAnchor(event) {
			event.preventDefault();
			let targetLink = event.target.getAttribute('href');
			let targetEl = document.querySelector(targetLink);

			if(targetEl) {
				targetEl.scrollIntoView({behavior : "smooth"});
			}

			if(this.isvisible) this.isvisible = false;
		},


	},
}
</script>

<style lang="scss" scoped>
@import '@/scss/HeaderView.scss';
</style>		