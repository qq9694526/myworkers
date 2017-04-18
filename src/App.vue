<template>
	<div id="app">
		<div class="swiper-container">
			<div class="swiper-wrapper">
				<div class="swiper-slide" v-for="worker in workers">
					<v-slider :worker="worker"></v-slider>
				</div>
			</div>
			<!-- 如果需要分页器 -->
			<div class="swiper-pagination"></div>
		</div>
	</div>
</template>

<script>
	import Swiper from 'swiper'
	import { DATA } from './assets/data.js'
	import vSlider from './components/slider/slider.vue'

	export default {
		name: 'app',
		data() {
			return {
				workers: DATA
			}
		},
		mounted() {
			var mySwiper = new Swiper('.swiper-container', {
				direction: 'vertical',
				loop: false,
				pagination: '.swiper-pagination',
				onSlideChangeEnd: function(swiper) {
					window.localStorage.slideId = swiper.activeIndex;
				}
			})
			var id = window.localStorage.slideId;
			if(id) {
				mySwiper.slideTo(id, 0);
			}
		},
		components: {
			vSlider
		}
	}
</script>

<style lang="less">
	@import './assets/swiper.min.css';
	#app,
	.swiper-container,
	.swiper-wrapper,
	.swiper-slide {
		height: 100%;
	}
	
	.swiper-pagination-bullet.swiper-pagination-bullet-active {
		/*background: #302E30;*/
		background-color: rgba(51,51,51,.8);
		height: 20px;
		border-radius: 4px;
	}
</style>