<template>
	<view class="main-color">
		<Search></Search>
		<view>
			<u-tabs height="92" active-color="#FB5F73" inactive-color="#666666" bar-height="4" :bold="false"
				font-size="30" :list="lists" :is-scroll="false" :current="current" @change="change"></u-tabs>
		</view>
		<view v-for="item in 15">
			<view class="coming-soon-top">
				周三
			</view>
			<view class="coming-soon-center">
				2021年10月27日
			</view>
			<view class="jingdong">
				<view class="left">
				</view>
				<view class="right">
					<view class="top">
						<view class="title">
							<text>007</text>
						</view>
						<view class="bottom">
							<view class="grade">评分：<span> 9.5</span></view>
						</view>
						<view>
							<view class="director">导演：<span>陈凯歌 徐克 林超贤</span></view>
						</view>
						<view>
							<view class="director act">主演：<span>吴京 易烊千玺 段奕宏 朱亚文…</span></view>
						</view>
						<view class="buy-ticket">
							预售
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import Search from "@/components/search"
	import banner from "@/static/banner.png"
	export default {
		data() {
			return {
				labelPosition: 'left',
				value: '',
				type: 'text',
				border: true,
				current: 1,
				lists: [{
					name: '热映'
				}, {
					name: '即将上映'
				}],
				listes: [{
						image: banner,
						title: '昨夜星辰昨夜风，画楼西畔桂堂东'
					},

					{
						image: 'https://cdn.uviewui.com/uview/swiper/1.jpg',
						title: '昨夜星辰昨夜风，画楼西畔桂堂东'
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/2.jpg',
						title: '身无彩凤双飞翼，心有灵犀一点通'
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/3.jpg',
						title: '谁念西风独自凉，萧萧黄叶闭疏窗，沉思往事立残阳'
					}
				],
				title: 'Hello'
			}
		},
		components: {
			Search
		},
		onLoad() {

		},
		methods: {
			change(index) {
				// uni.navigateBack()
				uni.switchTab({
							url: '/pages/index/index'
						})
			},
			openPage(path) {
				this.$u.route({
					url: path
				})
			},
		}
	}
</script>

<style lang="scss" scoped>
	@import "common/index.scss";
	.jingdong{
		margin-top: 30rpx;
		.left{
			width: 144rpx;
			height: 204rpx;
		}
		.buy-ticket{
			width: 120px;
			height: 56px;
			background: #3D8AF1 !important;
			border-radius: 28px;
		}
	}
</style>
