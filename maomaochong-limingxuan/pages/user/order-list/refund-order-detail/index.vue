<template>
	<view class="box">
		<view class="box-top">
			<view class="box-top-content">
				<view class="order-list-name">
					长津湖 （4张） <span>可调座</span>
				</view>
				<view class="order-list-date">
					 10月25日 18:34 - 21:23 国语2D 
				</view>
				<view class="order-list-site">
					环球国际影城（房山欢乐城店）
				</view>
				<view class="order-list-site">
					星空杜比vip厅
				</view>
				<view class="order-list-site">
					5排4座 5排5座 5排6座 5排7座
				</view>
			</view>
			<view class="box-top-img">
			</view>
		</view>
		<view class="box-center">
			<view class="box-center-icon">
				
			</view>
			<view class="box-center-describe" style="text-align: center;text-indent: 0;">
				非常抱歉，未能订票成功，资金已原路返回
			</view>
			<view class="box-center-describe">
				实付款：<span class="payment">¥42.23</span> 优惠 <span class="discounts">¥3.76</span>
			</view>
			<view class="box-center-payment">
				<span class="title">订单编号：</span>
				<span class="content">902628269659148288</span>
				<span class="copy">复制</span>
			</view>
		<view class="box-center-payment c-m-t">
			<span class="title">下单时间：</span>
			<span class="content">2021-10-26 18:42:30</span>
		</view>
		</view>
		<view class="box-bottom">
			观影须知<br>
			1.请提前到达影院现场，找到自助取票机，打印纸质电影票，完成取票
			<br>
			2.如现场自助取票机无法打印电影票，请联系影院工作人员处理。
			<br>
			3.凭打印好的纸质电影票，检票入场观影
			<br>
			4.特惠购票不支持改签、退票
		</view>
	</view>
</template>

<script>
</script>

<style lang="scss" scoped>
	@import "common/common.scss";
	page {
		height: 100%;
		background-color: #55595D;
	}
	.box{
		width: 710rpx;
		height: 1040rpx;
		background: #FFFFFF;
		border-radius: 8rpx;
		margin: 20rpx auto;
		.box-top{
			position: relative;
			display: flex;
			margin: 40rpx 20rpx 0;
			width: 670rpx;
			height: 298rpx;
			border-bottom: 2rpx solid #E8E8E8;
		.box-top-content{
		
			.order-list-name{
				margin-top: 40rpx;
				margin-left: 20rpx;
				height: 42rpx;
				font-size: 30rpx;
				font-family: PingFangSC-Medium, PingFang SC;
				font-weight: 500;
				color: #333333;
				line-height: 42rpx;
				& span{
					display: inline-block;
					padding: 4rpx;
					margin-left: 16rpx;
					border-radius: 2rpx;
					border: 1rpx solid #FB7C5F;
					height: 28rpx;
					font-size: 24rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #FB7C5F;
					line-height: 28rpx;
					text-align: center;
				}
			}
			.order-list-date{
				margin: 8rpx;
				margin-bottom: 10rpx;
				margin-left: 20rpx;
				height: 34rpx;
				font-size: 24rpx;
				font-family: PingFangSC-Regular, PingFang SC;
				font-weight: 400;
				color: #3D8AF1;
				line-height: 34rpx;
			}
			.order-list-site{
				margin-bottom: 14rpx;
				margin-left: 20rpx;
				height: 34rpx;
				font-size: 24rpx;
				font-family: PingFangSC-Regular, PingFang SC;
				font-weight: 400;
				color: #666666;
				line-height: 34rpx;
			}
		}
		.box-top-img{
			position: absolute;
			width: 144px;
			right: 20rpx;
			top: -138rpx;
			height: 204px;
			background: #D8D8D8;
			border-radius: 8px;
			background: url(../../../../static/movie.png) no-repeat 100% 100%;
		}
		}
		.box-center{
			height: 376rpx;
			margin: 0 20rpx ;
			border-bottom: 2rpx solid #E8E8E8;
			.box-center-icon{
				margin: 60rpx auto 26rpx;
				width: 82rpx;
				height: 82rpx;
				background: #999999;
				background: url(../../../../static/refund-icon.png) no-repeat 100% 100%;
			}
			.box-center-describe{
				height: 56rpx;
				font-size: 30rpx;
				font-family: PingFangSC-Medium, PingFang SC;
				font-weight: 500;
				color: #444444;
				line-height: 56rpx;
				text-indent: 130rpx;
			.payment{
				color:#FB5F73;
				margin-right: 34rpx;
			}
			.discounts{
				color:#FB7C5F;
			}
			}
			.box-center-payment{
				margin: 30rpx auto 12rpx;
				height: 40rpx;
				font-size: 30rpx;
				font-family: PingFangSC-Medium, PingFang SC;
				font-weight: 500;
				color: #666666;
				line-height: 40rpx;
				.title{
					margin-left: 130rpx;
					font-size: 24rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #444444;
				}
				.content{
					font-size: 24rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #444444;
				}
				.copy{
					display: inline-block;
					font-size: 24rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #3D8AF1;
					line-height: 34rpx;
					width: 80rpx;
					height: 40rpx;
					border-radius: 21rpx;
					border: 2rpx solid #3D8AF1;
					line-height: 40rpx;
					margin-left: 10rpx;
					text-align: center;
				}
	
			}
		}
		.box-bottom{
			margin-top: 20rpx;
			margin-left: 20rpx;
			width: 618rpx;
			height: 280rpx;
			font-size: 24rpx;
			font-family: PingFangSC-Regular, PingFang SC;
			font-weight: 400;
			color: #444444;
			line-height: 34rpx;
		}
	}
</style>
