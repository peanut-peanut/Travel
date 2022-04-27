<template>
	<div class="wrapper">
		<swiper :options="swiperOption">
			<swiper-slide v-for="item of swiperList" :key="item.id">
				<img class="swiper-img" :src=item.imgUrl>
			</swiper-slide>
			<div class="swiper-pagination" slot="pagination"></div>
		</swiper>
	</div>
</template>
<script>
export default{
	name: 'HomeSwiper',
	data (){
		return {
			swiperOption: {
				autoplay: 3000,
				pagination: '.swiper-pagination',
				loop: true
			},
			swiperList:[{
				id: '0001',
				imgUrl: 'https://imgs.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg'
			},{
				id: '0002',
				imgUrl: 'https://imgs.qunarzz.com/sight/source/1811/b8/5d599bbdcf8b57.jpg_r_640x214_2ee055e3.jpg'
			}]
		}
	}
}
</script>
<style lang="stylus" scoped>
	.wrapper >>> .swiper-pagination-bullet-active
		background: black !important
	.wrapper
		overflow: hidden
		width: 100%
		height: 0
		padding-bottom: 35.00%
		.swiper-img
			width: 100%

</style>
