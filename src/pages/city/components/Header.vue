<template>
	<div class="header">
		城市选择
		<router-link to='/'>
			<div class="iconfont header-back">&#xe601;</div>
		</router-link>
	</div>
</template>
<script>
export default {
	name: 'CityHeader'
}
</script>
<style lang="stylus" scoped>
@import '~styles/iconfont/varibles.styl';
	.header
		position relative
		height: $HeaderHeight
		line-height: $HeaderHeight
		overflow: hidden
		background-color: $bgColor
		text-align: center
		color: #fff
		font-size: .32rem
		.header-back
			position: absolute
			width: .64rem
			font-size: .4rem
			color: #fff
			top: 0
			left: 0
</style>
