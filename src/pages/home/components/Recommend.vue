<template>
	<div>
		<div class="title">热门榜单</div>
			<ul>
				<li class="item border-bottom" v-for="(item,index) of recommendList" :key="index">
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
	data () {
		return {
			recommendList: [{
				id: '0001',
				imgUrl: 'https://imgs.qunarzz.com/sight/p0/2109/b5/b5f465a57e638f34a3.water.jpg_200x200_5418f6cc.jpg',
				title: '北京环球度假区',
				desc: '北京环球度假区包含七大主题景区、37处骑乘娱乐设施及地标景点、24场娱乐演出、80家餐饮及30家零售门店，总面积超4平方千米，一期占地159.57公顷；二期占地165.83公顷，计划建设包含中国元素的主题公园，引入中国文化和孙悟空等IP；三期计划建设水上乐园。'
			},{
				id: '0002',
				imgUrl: 'https://imgs.qunarzz.com/sight/p0/2109/b5/b5f465a57e638f34a3.water.jpg_200x200_5418f6cc.jpg',
				title: '北京环球度假区',
				desc: '北京环球度假区包含七大主题景区、37处骑乘娱乐设施及地标景点、24场娱乐演出、80家餐饮及30家零售门店，总面积超4平方千米，一期占地159.57公顷；二期占地165.83公顷，计划建设包含中国元素的主题公园，引入中国文化和孙悟空等IP；三期计划建设水上乐园。'
			},{
				id: '0003',
				imgUrl: 'https://imgs.qunarzz.com/sight/p0/2109/b5/b5f465a57e638f34a3.water.jpg_200x200_5418f6cc.jpg',
				title: '北京环球度假区',
				desc: '北京环球度假区包含七大主题景区、37处骑乘娱乐设施及地标景点、24场娱乐演出、80家餐饮及30家零售门店，总面积超4平方千米，一期占地159.57公顷；二期占地165.83公顷，计划建设包含中国元素的主题公园，引入中国文化和孙悟空等IP；三期计划建设水上乐园。'
			},{
				id: '0004',
				imgUrl: 'https://imgs.qunarzz.com/sight/p0/2109/b5/b5f465a57e638f34a3.water.jpg_200x200_5418f6cc.jpg',
				title: '北京环球度假区',
				desc: '北京环球度假区包含七大主题景区、37处骑乘娱乐设施及地标景点、24场娱乐演出、80家餐饮及30家零售门店，总面积超4平方千米，一期占地159.57公顷；二期占地165.83公顷，计划建设包含中国元素的主题公园，引入中国文化和孙悟空等IP；三期计划建设水上乐园。'
			}]
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

