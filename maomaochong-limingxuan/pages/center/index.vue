<template>
	<view class="main-color">
		<view class="wrap">
			<view class="left">
				<view class="left-view">
					<view class="left-view-img">

					</view>
				</view>
				<view class="right-view">
					北京
					<view class="triangle-down">

					</view>
				</view>
			</view>
			<view class="right">
				<u-input height="48" class="input-icon" v-model="value" :type="type" :border="border"
					placeholder="搜影片" />
				<view class="input-imgs" />
			</view>
		</view>
		<view>
			<u-tabs height="92" active-color="#666666" inactive-color="#666666" bar-height="4" :bold="false"
				font-size="30" :list="lists" :is-scroll="false" :current="current" @change="change"></u-tabs>
		</view>
		<view v-for="item in 30">
		<view  class="movie-content">
			<view class="movie-content-left">
				<view class="movie-left-top">
					环球国际影城（房山欢乐城店）
				</view>
				<view class="movie-left-bottom">
					房山区兴房大街38号华冠欢乐城四楼
				</view>
			</view>
			<view class="movie-content-right">
				<view class="movie-right-top">
					<span>¥38</span>
					起
				</view>
				<view class="movie-right-bottom">
					3.45KM
				</view>
			</view>
		</view>
		<view class="drag">
			
		</view>
		</view>
	</view>
</template>

<script>
	import banner from "@/static/banner.png"
	export default {
		data() {
			return {
				labelPosition: 'left',
				value: '',
				type: 'text',
				border: true,
				current: 0,
				lists: [{
					name: '全城'
				}, {
					name: '品牌'
				}],
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {
			change(index) {

				this.current = index;
				// this.$u.route({
				// 	url: 'pages/coming-soon/index'
				// })
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

	.movie-content {
		margin-left: 20rpx;
		display: flex;
		width: 710rpx;
		height: 128rpx;
		background: #FFFFFF;
		border-radius: 10rpx;

		.movie-content-left {
			width: 604rpx;
			margin-left: 20rpx;
			margin-top: 22rpx;

			.movie-left-top {
				font-size: 30rpx;
				font-family: PingFangSC-Medium, PingFang SC;
				font-weight: 500;
				color: #333333;
				margin-bottom: 8rpx;
			}

			.movie-left-bottom {
				font-size: 24rpx;
				font-family: PingFangSC-Regular, PingFang SC;
				font-weight: 400;
				color: #666666;
			}

		}

		.movie-content-right {
			margin: 22rpx 18rpx 0 0;
			text-align: right;
			.movie-right-top {
		font-size: 24rpx;
		font-family: PingFangSC-Regular, PingFang SC;
		font-weight: 400;
		color:#666666;
				margin-bottom: 16rpx;
				& span{
					color: #FB5F73;
				}
			}

			.movie-right-bottom {
				font-size: 24rpx;
				font-family: PingFangSC-Regular, PingFang SC;
				font-weight: 400;
				color: #666666;
			}
		}
	}
	.drag{
		height: 20rpx;
		// background: #FFFFFF;
	}
	.main-color{
		background-color: #F9FAFB;
	}
	page {
		background-color: #F9FAFB;
	}
	/deep/.u-tab-item {
		background-color: #F9FAFB;	}
</style>
