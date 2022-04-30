<template>
	<div>
		<div class="title">周末去哪儿</div>
			<ul>
				<li class="item border-bottom" v-for="(item,index) of list" :key="index">
					<div class="item-img-wrapper">
						<img class="item-img" :src=item.imgUrl>
					</div>
					<div class="item-info">
						<p class="item-title">{{item.title}}</p>
						<p class="item-desc">{{item.desc}}</p>
					</div>
				</li>
			</ul>
	</div>
</template>
<script>
export default {
	name: 'HomeWeekend',
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
	.item-img-wrapper
		overflow: hidden
		height: 0
		padding-bottom: 33.43%
		.item-img
			width: 100%
	.item-info
		padding: .1rem
		.item-title
			line-height: .4rem
			font-size: .32rem
		.item-desc
			margin-top: .1rem
			line-height: .4rem
			ellipsis()
			color: #ccc
</style>

