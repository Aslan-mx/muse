<template>
	<view>
		<view style="height: 298rpx;margin-bottom: 28rpx;">
			<view class="user-top">
				<view class="user-img"></view>
				<view class="user-name">
					<view class="names">小喵熊</view>
					<view class="ids">ID 287698</view>
				</view>
			</view>
			<view class="share">
				<view style="height: 36rpx;"></view>
				<view class="share-top">
					可提现：
					<span class="share-money">¥0.00</span>
					<span class="cash-out">提现</span>
				</view>
				<view class="share-bottom">
					分享给好友可以获得红包奖励
				</view>
				<view class="come-share">
					立即分享
				</view>
			</view>
		</view>
		<view class="order-list">
			<view class="user-order">
				<view class="user-order-left">
					我的订单
				</view>
				<view class="user-order-right" @click="handleGoOrderList">
					全部订单<u-icon name="arrow-right" color="#999999" size="28"></u-icon>
				</view>
			</view>
			<view class="user-order-card">
				<u-grid :col="4" :border="false">
					<u-grid-item>
						<u-icon name="photo" :size="46"></u-icon>
						<view class="grid-text">待付款</view>
					</u-grid-item>
					<u-grid-item>
						<u-icon name="lock" :size="46"></u-icon>
						<view class="grid-text">待出票</view>
					</u-grid-item>
					<u-grid-item>
						<u-icon name="hourglass" :size="46"></u-icon>
						<view class="grid-text">已出票</view>
					</u-grid-item>
					<u-grid-item>
						<u-icon name="hourglass" :size="46"></u-icon>
						<view class="grid-text">退款/售后</view>
					</u-grid-item>
				</u-grid>
			</view>
		</view>
		<view class="order-list more-features">
			<view class="user-order">
				<view class="user-order-left">
					更多功能
				</view>
			</view>
			<view class="more-features-list">
				<u-cell-group :border="false">
					<u-cell-item :border-bottom="false" icon="email" title="邀请好友"></u-cell-item>
					<u-cell-item :border-bottom="false" icon="email" title="在线客服"></u-cell-item>
					<u-cell-item :border-bottom="false" icon="email" title="建议反馈"></u-cell-item>
				</u-cell-group>
			</view>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				pic: 'https://uviewui.com/common/logo.png',
				show: true
			}
		},
		onLoad() {

		},
		methods: {
			handleGoOrderList() {
				this.$u.route({
					url: 'pages/user/order-list/index'
				})
			},
		}
	}
</script>

<style lang="scss" scoped>
	page {
		background-color: #F9FAFB;
	}

	.user-top {
		display: flex;
		width: 750rpx;
		height: 259rpx;
		background: #FB5F73;

		.user-img {
			margin: 42rpx 28rpx 0 20rpx;
			width: 72rpx;
			height: 72rpx;
			background: url(../../static/users.png) no-repeat;
			background-size: 72rpx 72rpx;
			box-shadow: 0rpx 0rpx 8rpx 0rpx rgba(251, 95, 115, 0.29);
			border: 2rpx solid #FB5F73;
			border-radius: 50%;
		}

		.user-name {
			margin-top: 42rpx;

			.names {
				font-size: 24rpx;
				font-family: PingFangSC-Medium, PingFang SC;
				font-weight: 500;
				color: #FFFFFF;
			}

			.ids {
				font-size: 24rpx;
				font-family: PingFangSC-Regular, PingFang SC;
				font-weight: 400;
				color: #FFFFFF;
			}
		}
	}

	.share {
		margin: -112rpx auto 0;
		width: 710rpx;
		height: 160rpx;
		background: #FFFFFF;
		box-shadow: 0 0 8rpx 0 rgba(0, 0, 0, 0.13);
		border-radius: 8rpx;
		position: relative;

		.share-top {
			font-size: 30rpx;
			font-family: PingFangSC-Regular, PingFang SC;
			font-weight: 400;
			color: #333333;
			margin: 0 0 10rpx 20rpx;

			.share-money {
				color: #FB5F73;
			}
		}

		.share-bottom {
			height: 34rpx;
			font-size: 24rpx;
			font-family: PingFangSC-Regular, PingFang SC;
			font-weight: 400;
			color: #666666;
			margin-left: 20rpx;
		}

		.cash-out {
			display: inline-block;
			text-align: center;
			margin-left: 20rpx;
			width: 72rpx;
			height: 36rpx;
			border-radius: 18rpx;
			border: 1px solid #FB5F73;
			font-size: 24rpx;
			font-family: PingFangSC-Regular, PingFang SC;
			font-weight: 400;
			color: #FB5F73;
			line-height: 36rpx;
		}

		.come-share {
			text-align: center;
			top: 54rpx;
			right: 40rpx;
			position: absolute;
			width: 132rpx;
			height: 56rpx;
			font-size: 24rpx;
			font-family: PingFangSC-Regular, PingFang SC;
			font-weight: 400;
			color: #FFFFFF;
			line-height: 56rpx;
			background: #FB5F73;
			border-radius: 8rpx;

		}
	}

	.order-list {
		margin: 0 auto;
		width: 710rpx;
		height: 258rpx;
		background: #FFFFFF;
		box-shadow: 0rpx 0rpx 8rpx 0rpx rgba(0, 0, 0, 0.13);
		border-radius: 8rpx;

		.user-order {
			display: flex;
			position: relative;
			margin: 0 auto;
			width: 670rpx;
			height: 80rpx;
			line-height: 80rpx;
			border-bottom: 2rpx solid #E8E8E8;

			.user-order-left {
				font-size: 30rpx;
				font-family: PingFangSC-Regular, PingFang SC;
				font-weight: 400;
				color: #444444;
			}

			.user-order-right {
				position: absolute;
				right: 0rpx;
				font-size: 24rpx;
				font-family: PingFangSC-Regular, PingFang SC;
				font-weight: 400;
				color: #666666;
			}
		}

		.user-order-card {
			margin-top: 20rpx;

			.grid-text {
				font-size: 28rpx;
				margin-top: 4rpx;
				color: #666666;
			}
		}

	}

	.more-features {
		margin: 20rpx auto 0;
		width: 710rpx;
		height: 344rpx;
		background: #FFFFFF;
		box-shadow: 0rpx 0rpx 8rpx 0rpx rgba(0, 0, 0, 0.13);
		border-radius: 8rpx;

		.more-features-list {
			/deep/.u-cell {
				height: 80rpx;
				padding: 0 20rpx;
				line-height: 80rpx;
				font-size: 30rpx;
				font-family: PingFangSC-Regular, PingFang SC;
				font-weight: 400;
				color: #444444;

				.u-cell__left-icon-wrap {
					margin-right: 20rpx;
					font-size: 30rpx;
				}
			}
		}
	}
</style>
