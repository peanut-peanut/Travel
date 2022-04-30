<template>
	<div>
		<div class="title">热门榜单</div>
			<ul>
				<li class="item border-bottom" v-for="(item,index) of list" :key="index">
					<img class="item-img" :src=item.imgUrl>
					<div class="item-info">
						<p class="item-title">{{item.title}}</p>
						<p class="item-desc">{{item.desc}}</p>
						<button class="item-button">查看详情</button>
					</div>
				</li>
			</ul>
	</div>
</template>
<script>
export default {
	name: 'HomeRecommend',
	props: {
		list: Array
	},
	data () {
		return {
		}
	}
}
</script>
<style lang="stylus" scoped>
	@import '~styles/iconfont/mixins.styl'
	.title
		font-size: .3rem
		line-height: .6rem
		text-indent: .2rem
		background-color: #eee
	.item
		overflow: hidden
		display: flex
		height: 1.9rem
		.item-img
			width: 1.7rem
			height: 1.7rem
			padding: .1rem
		.item-info
			flex: 1
			min-width: 0
			padding: .1rem
			.item-title
				line-height: .5rem
				font-size: .32rem
			.item-desc
				margin-top: .2rem
				line-height: .4rem
				ellipsis()
				color: #ccc
			.item-button
				background-color: #ff9300
				color: #fff
				padding: 0 .1rem
				border-radius: .06rem
				margin-top: .2rem
</style>

