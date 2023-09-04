<template>
	<section id="header">
		<header>
			<div class="logo_box">
				<img src = "http://placehold.it/50X50" />
			</div>
			<nav>
				<ul>
					<li><a href="#">더미 메뉴</a></li>
					<li><a href="#">더미 메뉴</a></li>
					<li><a href="#">더미 메뉴</a></li>
					<li><a href="#">더미 메뉴</a></li>
					<li><a href="#">더미 메뉴</a></li>
				</ul>
			</nav>
		</header>
		<aside>
			<div class="icon_box">
				<i class="fa-brands fa-square-instagram"></i> 
				<i class="fa-brands fa-instagram"></i>

				<i class="fa-regular fa-envelope-open"></i>	

				<i class="fa-solid fa-phone"></i>
			</div>
		</aside>
	</section>
</template>

<style lang="scss" scoped>
@import '@/scss/mixin.scss';

#header {

	header {
		width: 94%;
		height: 100px;
		margin: 0 auto;
		position: fixed;
		top: 30px;
		left: 3%;
		border: 1px solid #333;
		backdrop-filter: blur(5px);
		
		@include center-sb;

		.logo_box {

		}

		nav {

			ul {
				width: 600px;
				margin-right: 50px;
				@include center-sb
			}
		}
	}

	aside {
		width: 100px;
		height: 600px;
		position: fixed;
		top: 131px;
		left: 3%;
		border-left: 1px solid #333;
		border-right: 1px solid #333;
		border-bottom: 1px solid #333; 
		backdrop-filter: blur(5px);
		display: flex;
		justify-content: center;
		align-items: flex-end;

		.icon_box {
			height: 300px;

			@include c-center-se;

			i {
				font-size: 30px;
			}
		}
	}
}
</style>		