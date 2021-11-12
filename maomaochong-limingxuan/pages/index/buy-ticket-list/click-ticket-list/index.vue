<template>
	<view>
		<view class="movie-bg">
			<view class="movie-bg-name">
				环球国际影城（房山欢乐城店）
			</view>
			<view class="movie-bg-land">
				房山区兴房大街38号华冠欢乐城四楼
			</view>
		</view>
		<view class="movie-banner">
			<u-swiper :current="swiperCurrent" @click="handleClickBg" mode="none" bg-color="#F9FAFB" :autoplay="false"
				height="240" :effect3d="true" :circular="true" :list="listes" @change="handleChangeBg">
			</u-swiper>
			<view class="banner-detail">
				<view class="banner-detail-name">
					{{ bannerName }}
				</view>
				<view class="banner-detail-detail">
					176分钟 ｜ 剧情，历史，战争 ｜ 2
				</view>
			</view>
			<u-tabs font-size="24" height="76" bar-width="32" bar-height="4" :list="list" :is-scroll="false"
				:bold="false" inactive-color="#333333" active-color="#FB5F73" :current="current" @change="change">
			</u-tabs>
			<view class="bt-ticket" v-for="item in 10">
				<view class="bt-ticket-date">
					<view class="bt-ticket-date-start">
						16:10
					</view>
					<view class="bt-ticket-date-end">
						19:06分散场
					</view>
				</view>
				<view class="bt-ticket-place">
					<view class="bt-ticket-place-name">
						国语2D
					</view>
					<view class="bt-ticket-places">
						星空杜比VIP厅
					</view>

				</view>
				<view class="bt-ticket-price">
					<view class="bt-ticket-price-money">
						<span class="bt-ticket-price-end">￥64.5</span><span class="bt-ticket-price-start">¥75.34</span>
					</view>
					<view class="bt-ticket-price-discounts">
						¥10.84
					</view>
				</view>
				<view class="bt-ticket-click" @click="handleClickByTicket">
					购票
				</view>
			</view>
		</view>
		<view>
			<u-modal :title="title" :confirm-text="confirmText" v-model="show" :content="content" @confirm="handleConfirm"></u-modal>
		</view>
	</view>
</template>

<script>
	import banner from "@/static/banner.png"
	export default {
		data() {
			return {
				confirmText: '我知道啦',
				title: "自动调座规则",
				show: false,
				content: '第三方服务商出票，由于出票过程存在时间差，可能存在已选座位被占情况。为了不耽误您的时间，我们将按照优先选取从(银幕中央-核心区域-边缘)的顺序为您调换座位。购买多张票时将继续为您保持连座。',
				list: [{
						name: '待收货'
					},
					{
						name: '待付款'
					}, {
						name: '待评价'
					}
				],
				bannerName: '',
				labelPosition: 'left',
				value: '',
				type: 'text',
				border: true,
				current: 0,
				swiperCurrent: 0,
				lists: [{
					name: '热映',
					list: [{
							name: '10月9日'
						},
						{
							name: '10月10日'
						}, {
							name: '10月11日'
						}
					],
				}, {
					name: '即将上映'
				}],
				listes: [{
						image: banner,
						list: [{
								name: '10月9日'
							},
							{
								name: '10月10日'
							}, {
								name: '10月11日'
							}
						],
						title: '长津湖'
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/1.jpg',
						list: [{
								name: '10月9日'
							},
							{
								name: '10月10日'
							}
						],
						title: '007'
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/2.jpg',
						list: [{
								name: '10月9日'
							},
							{
								name: '10月10日'
							}
						],
						title: '变形金刚'
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/3.jpg',
						list: [{
								name: '10月9日'
							},
							{
								name: '10月10日'
							}
						],
						title: '蜘蛛侠'
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/3.jpg',
						list: [{
								name: '10月9日'
							},
							{
								name: '10月10日'
							}
						],
						title: '猪猪侠'
					},
				]
			}
		},
		onLoad() {
			this.bannerName = this.listes[0].title
		},
		methods: {
			handleConfirm() {
				this.$u.route({
					url: 'pages/select/index'
				})
			},
			handleClickByTicket() {
				this.show = true;
			},
			change(index) {
				this.current = index;
			},
			handleClickBg(index) {
				this.swiperCurrent = index
				console.log(`点击了第${index + 1}张图片`)
				// this.$refs.uToast.show({
				// 	title: `点击了第${index + 1}张图片`,
				// 	type: 'success'
				// })
			},
			handleChangeBg(index) {
				this.bannerName = this.listes[index].title
				this.list = this.listes[index].list
				console.log(this.listes[index].title)
			},
			handleGoTicketList() {
				this.$u.route({
					url: 'pages/index/buy-ticket-list/index'
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
	/deep/.uni-swiper-slides {
		
		width: 175rpx !important;
		height: 240rpx;
		 left: 50% !important;
		margin-left: -88rpx;
		top: 0 !important;
		right: 50% !important;
		 bottom: 0 !important;
	}

	page {
		height: 100%;
		background-color: #F9FAFB;
	}

	.movie-bg {
		padding-top: 24rpx;
		text-align: center;
		margin: 20rpx;
		width: 710rpx;
		height: 116rpx;
		border-radius: 8rpx;
		background: url(../../../../static/movie-bg.png) no-repeat;

		.movie-bg-name {
			height: 42rpx;
			font-size: 30rpx;
			font-family: PingFangSC-Medium, PingFang SC;
			font-weight: 500;
			color: #FFFFFF;
			line-height: 42rpx;
		}

		.movie-bg-land {
			height: 34rpx;
			font-size: 24rpx;
			font-family: PingFangSC-Regular, PingFang SC;
			font-weight: 400;
			color: #FFFFFF;
			line-height: 34rpx;
		}
	}

	.movie-banner {
		.banner-detail {
			
			text-align: center;

			.banner-detail-name {
				height: 42rpx;
				font-size: 30rpx;
				font-family: PingFangSC-Medium, PingFang SC;
				font-weight: 500;
				color: #333333;
				
				line-height: 42rpx;
				margin-bottom: 20rpx;
				margin-top: 26rpx;
			}

			.banner-detail-detail {
				height: 34rpx;
				font-size: 24rpx;
				font-family: PingFangSC-Medium, PingFang SC;
				font-weight: 500;
				color: #666666;
				line-height: 34rpx;
			}
		}

		.bt-ticket {
			position: relative;
			display: flex;
			width: 710rpx;
			height: 140rpx;
			background: #FFFFFF;
			border-radius: 10rpx;
			margin: 20rpx auto;

			.bt-ticket-date {
				margin-left: 20rpx;
				margin-right: 20rpx;

				.bt-ticket-date-start {
					height: 42rpx;
					font-size: 30rpx;
					font-family: PingFangSC-Medium, PingFang SC;
					font-weight: 500;
					color: #333333;
					line-height: 42rpx;
					margin: 22rpx 0 10rpx;
				}

				.bt-ticket-date-end {
					height: 34rpx;
					font-size: 24rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #666666;
					line-height: 34rpx;
				}
			}

			.bt-ticket-place {
				width: 182rpx;
				margin: 26rpx 40rpx 0 0;

				.bt-ticket-place-name {
					height: 34rpx;
					margin-bottom: 14rpx;
					font-size: 24rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #333333;
					line-height: 34rpx;
				}

				.bt-ticket-places {
					height: 34rpx;
					font-size: 24rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #666666;
					line-height: 34rpx;
				}
			}

			.bt-ticket-price {
				margin-top: 22rpx;

				.bt-ticket-price-money {
					margin-bottom: 10rpx;
					height: 42rpx;
					font-size: 30rpx;
					font-family: PingFangSC-Medium, PingFang SC;
					font-weight: 500;
					color: #FB5F73;
					line-height: 42rpx;

					.bt-ticket-price-end {}

					.bt-ticket-price-start {
						color: #3D8AF1;
						font-size: 24rpx;
						margin-left: 18rpx;
					}
				}

				.bt-ticket-price-discounts {
					margin-left: 12rpx;
					height: 34rpx;
					font-size: 24rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #666666;
					line-height: 34rpx;
				}
			}

			.bt-ticket-click {
				position: absolute;
				text-align: center;
				width: 96rpx;
				height: 48rpx;
				line-height: 48rpx;
				background: #FB5F73;
				border-radius: 28rpx;
				top: 46rpx;
				right: 20rpx;
				font-size: 24rpx;
				font-family: PingFangSC-Medium, PingFang SC;
				font-weight: 500;
				color: #FFFFFF;
			}
		}
	}
</style>
