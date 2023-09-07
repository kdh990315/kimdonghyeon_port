<template>
	<section id="header">
		<header>
			<div class="logo_box">
				<img src="http://placehold.it/100x100" />
			</div>
			<nav>
				<ul>
					<li v-for="(menu, index) in headerMenu" :key="index">
						<a :href="menu.url"><span>.0{{ index + 1}}</span>{{ menu.menu }}</a>
					</li>
				</ul>
			</nav>

			<div class="header_mobile_nav" @click="HeaderMobileEvent" :class="{ show: isvisible }">
				<span></span>
			</div>

			<div class="header_moblie" :class="{ show: isvisible }">
				<ul>
					<li v-for="(menu, index) in headerMenu" :key="index">
						<a :href="menu.url">{{ menu.menu }}</a>
					</li>
					<li>
						<a href="#">
							<i class="fa-brands fa-square-instagram"></i>
						</a>
						<a href="#">
							<i class="fa-brands fa-instagram"></i>
						</a>
						<a href="#">
							<i class="fa-regular fa-envelope-open"></i>
						</a>
						<a href="#">
							<i class="fa-solid fa-phone"></i>
						</a>
					</li>
				</ul>
			</div>

		</header>
		<aside>
			<div class="icon_box">
				<a href="#">
					<i class="fa-brands fa-square-instagram"></i>
				</a>
				<a href="#">
					<i class="fa-brands fa-instagram"></i>
				</a>
				<a href="#">
					<i class="fa-regular fa-envelope-open"></i>
				</a>
				<a href="#">
					<i class="fa-solid fa-phone"></i>
				</a>
			</div>
		</aside>
	</section>
</template>

<script>
export default {
	data() {
		return {
			headerMenu: [
				{menu: 'dummy', url: '#'},
				{menu: 'dummy', url: '#'},
				{menu: 'dummy', url: '#'},
				{menu: 'dummy', url: '#'},
				{menu: 'dummy', url: '#'},
			],

			isvisible: false,

		}
	},
	methods: {
		HeaderMobileEvent() {
			this.isvisible = !this.isvisible;
		}
	}
}
</script>

<style lang="scss" scoped>
@import '@/scss/mixin.scss';
@import '@/scss/HeaderView.scss';
</style>		