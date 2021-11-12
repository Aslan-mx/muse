<template>
	<view class="wrap">
		<view class="left" @click="handlePlace">
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
			}
		},
		components: {
			Search
		},
		onLoad() {

		},
		methods: {
			handlePlace() {
				this.$u.route({
					url: 'pages/index/place/index'
				})
			},
			handleGoTicketList() {
				this.$u.route({
					url: 'pages/index/buy-ticket-list/index'
				})
			},
			change(index) {
				// this.current = index;
				this.$u.route({
					url: 'pages/coming-soon/index'
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
	.wrap {
		height: 80rpx;
		display: flex;
	
		.left {
			width: 332rpx;
			display: flex;
	
			.left-view {
				width: 84rpx;
				height: 80rpx;
	
				.left-view-img {
					margin: 18rpx 0 0 24rpx;
					width: 40rpx;
					height: 29rpx;
					background: url(../../static/live-streaming.png) no-repeat;
				}
			}
			.right-view{
				display: flex;
				margin-top: 16rpx;
				height: 34rpx;
				font-size: 24rpx;
				font-family: PingFangSC-Medium, PingFang SC;
				font-weight: 500;
				color: #666666;
				line-height: 34rpx;
				.triangle-down{
					margin-left: 6rpx;
					margin-top: 12rpx;
					   width: 0;
					    height: 0;
					    border-left: 6rpx solid transparent;
					    border-right: 6rpx solid transparent;
					    border-top: 8rpx solid #666666;
				}
			}
		}
	
		.right {
			position: relative;
			width: 418rpx;
			width: 200px;
	
			.u-input {
				margin-top: 10rpx;
				background: #F9FAFB;
				border-radius: 24rpx;
				width: 400rpx;
				font-size: 24rpx;
				font-family: PingFangSC-Regular, PingFang SC;
				font-weight: 400;
				color: #999999;
				border: 1px solid $m-main-color;
			}
	
			.input-icon {
				text-indent: 38rpx;
			}
	
			.input-imgs {
				width: 20rpx;
				height: 20rpx;
				left: 20rpx;
				top: 24rpx;
				position: absolute;
				background: url(../../static/search.png) no-repeat 100%;
			}
		}
	}
</style>
