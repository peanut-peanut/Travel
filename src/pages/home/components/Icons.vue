<template>
	<div class="icons">
		<swiper :options="swiperOption">
			<swiper-slide v-for="(page,index) of pages" :key="index">
				<div class="icon" v-for="item of page" :key="item.id">
					<div class="icon-img">
						<img class="icon-img-content" :src=item.imgUrl>
					</div>
					<p class="icon-desc">{{item.desc}}</p>
				</div>
			</swiper-slide>
		</swiper>
	</div>
</template>
<script>
export default{
	name: 'HomeIcons',
	data () {
		return {
			swiperOption: {
				autoplay: false
			},
			iconList: [{
				id: '0001',
				imgUrl: '//s.qunarzz.com/homenode/images/touchheader/hotel.png',
				desc: '酒店'
				},{
				id: '0002',
				imgUrl: '//s.qunarzz.com/homenode/images/touchheader/hotel.png',
				desc: '酒店'
				},{
				id: '0003',
				imgUrl: '//s.qunarzz.com/homenode/images/touchheader/hotel.png',
				desc: '酒店'
				},{
				id: '0004',
				imgUrl: '//s.qunarzz.com/homenode/images/touchheader/hotel.png',
				desc: '酒店'
				},{
				id: '0005',
				imgUrl: '//s.qunarzz.com/homenode/images/touchheader/hotel.png',
				desc: '酒店'
				},{
				id: '0006',
				imgUrl: '//s.qunarzz.com/homenode/images/touchheader/hotel.png',
				desc: '酒店'
				},{
				id: '0007',
				imgUrl: '//s.qunarzz.com/homenode/images/touchheader/hotel.png',
				desc: '酒店'
				},{
				id: '0008',
				imgUrl: '//s.qunarzz.com/homenode/images/touchheader/hotel.png',
				desc: '酒店'
				},{
				id: '0009',
				imgUrl: '//s.qunarzz.com/homenode/images/touchheader/hotel.png',
				desc: '酒店'
				},{
				id: '0010',
				imgUrl: '//s.qunarzz.com/homenode/images/touchheader/hotel.png',
				desc: '酒店'
				},{
				id: '0011',
				imgUrl: '//s.qunarzz.com/homenode/images/touchheader/hotel.png',
				desc: '酒店'
				},{
				id: '0012',
				imgUrl: '//s.qunarzz.com/homenode/images/touchheader/hotel.png',
				desc: '酒店'
				}					
			]
		}
	},
	computed: {
		pages () {
			const pages = []
			this.iconList.forEach((item,index)  => {
				let page=Math.floor(index/10)
				if(!pages[page]){
					pages[page] = []
				}
				pages[page].push(item)
			})
			return pages
		}
	}
}
</script>
<style lang="stylus" scoped>
	@import '~styles/iconfont/varibles.styl'
	@import '~styles/iconfont/mixins.styl'
	.icons >>> .swiper-container
		height: 0
		padding-bottom: 50%
	.icon
		overflow: hidden
		float: left
		width: 20%
		height: 0
		padding-bottom: 25%
		height: 100%
		position relative
		.icon-img
			position: absolute
			top: 0
			left: 0
			right: 0
			bottom: .44rem
			box-sizing: border-box
			padding: .1rem
			.icon-img-content
				display: block
				margin: 0 auto
				height: 100%
		.icon-desc
				position: absolute
				text-align: center
				left: 0
				right: 0
				bottom: 0
				height: .44rem
				line-height: .44rem
				color: $dartTextColor
				ellipsis()
</style>
