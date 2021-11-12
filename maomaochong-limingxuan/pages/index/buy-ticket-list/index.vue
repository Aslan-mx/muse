<template>
	<view>
	<view class="ticket-list">
		<view class="ticket-list-detail">
			<view class="ticket-list-detail-left">
				
			</view>
			<view class="ticket-list-detail-right">
				<view class="ticket-detail-name">
					长津湖
				</view>
				<view class="ticket-detail-divide-equally">
					评分：<span>9.5</span> 
				</view>
				<view class="ticket-detail-director">
					导演： 陈凯歌 徐克 林超贤
				</view>
				<view class="ticket-detail-protagonist">
					主演： 吴京 易烊千玺 段奕宏 朱亚文…
				</view>
			</view>
		</view>
		<view class="ticket-list-date">
			<u-tabs 
			font-size="24" 
			height="76" 
			bar-width="32" 
			bar-height="4" 
			:list="list" 
			:is-scroll="false" 
			:bold="false"
			inactive-color="#333333"
			active-color="#FB5F73"
			:current="current" 
			@change="change"
			></u-tabs>
		</view>
	</view>
<view>
	<view v-for="item in 30">
	<view  class="movie-content" @click="handleGoClickTicketList">
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
</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
					name: '今天10月25日'
				}, {
					name: '明天10月26日'
				}, {
					name: '后天10月27日',
				},
				{
					name: '10月28日',
				},
				],
				current: 0
			}
		},
		methods: {
			change(index) {
				this.current = index;
			},
			handleGoClickTicketList() {
				this.$u.route({
					url: 'pages/index/buy-ticket-list/click-ticket-list/index'
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	page {
		height: 100%;
		background-color: #F9FAFB;
	}
	.ticket-list{
		margin: 20rpx;
		width: 710rpx;
		height: 300rpx;
		background: #FFFFFF;
		.ticket-list-detail{
			display: flex;
			height: 224rpx;
			padding-top: 20rpx;
			margin: 20rpx 0 0 20rpx;
			.ticket-list-detail-left{
				margin-right: 40rpx;
				width: 144rpx;
				height: 204rpx;
				background: url(../../../static/movie.png) no-repeat;
				border-radius: 8rpx;
			}
			.ticket-list-detail-right{
				.ticket-detail-name{
					height: 42rpx;
					font-size: 30rpx;
					font-family: PingFangSC-Medium, PingFang SC;
					font-weight: 500;
					color: #333333;
					line-height: 42rpx;
				}
				.ticket-detail-divide-equally{
					height: 42rpx;
					font-size: 24rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #666666;
					line-height: 34rpx;
					margin: 14rpx 0 18rpx 0;
					& span{
						color: #FF6521;
						font-size: 30rpx;
					}
				}
				.ticket-detail-director{
					margin-bottom: 10rpx;
					height: 34rpx;
					font-size: 24rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #666666;
					line-height: 34rpx;
				}
				.ticket-detail-protagonist {
					width: 416rpx;
					height: 34rpx;
					font-size: 24rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #666666;
					line-height: 34rpx;
				}
			}
		}
	.ticket-list-date{
		height: 76rpx;
	}
	}
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
		 //background: red;
	}
	.main-color{
		background-color: #F9FAFB;
	}
</style>
