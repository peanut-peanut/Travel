<template>
		<div class="header">
			<div class="header-left">
				<div class="iconfont back-icon">&#xe601;</div>
			</div>
			<div class="header-input">
				<span class="iconfont">&#xe600;</span>
				请输入城市/景点/游玩主题
			</div>
			<router-link to='/city'>
				<div class="header-right">
					{{this.city}}
					<span class="iconfont arrow-right">&#xe6dc;</span>
				</div>
			</router-link>
		</div>
</template>
<script>
export default{
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/iconfont/varibles.styl'
	/* 1rem = html font-size = 50px */
	.header
		display: flex
		height: $HeaderHeight
		line-height: $HeaderHeight
		color: #fff
		background-color: $bgColor
		.header-left
			width: .64rem
			float: left
			.back-icon
				margin-left: .3rem
				font-size: .4rem
		.header-input
			flex: 1
			height: .62rem
			line-height: .62rem
			margin-top: .12rem
			margin-left: .2rem
			padding-left: .2rem
			border-radius: .1rem
			background-color: #fff
			color: #ccc
		.header-right
			width: 1.24rem
			float: right
			text-align: center
			color: #fff
			.arrow-right
				margin-left: -.02rem
				font-size: .24rem
</style>
