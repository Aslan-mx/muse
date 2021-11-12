<template>
	<view class="box">
		<view class="box-info">
			<view class="box-info-top">
				<view class="info-let">

				</view>
				<view class="info-right">
					<view class="info-name">
						长津湖 （4张）
					</view>
					<view class="info-date">
						10月25日 18:34 - 21:23
					</view>
					<view class="info-place">
						环球国际影城（房山欢乐城店）
					</view>
					<view class="info-land">
						星空杜比vip厅 <span>5排4座 5排5座 5排6座 5排7座</span>
					</view>
				</view>
			</view>
			<view class="box-info-rules">
				<span class="rules-1">不支持退票</span>
				<span class="rules-2">不支持改签</span>
				<span class="rules-3">影票原价¥ 200.00</span>
			</view>
		</view>
		<view class="box-select">
			<view class="box-select-radio">
				<view class="">
					自动调座
					<u-radio-group v-model="value" @change="radioGroupChange" style="margin-left: 154rpx;">
						<u-radio @change="radioChange" v-for="(item, index) in list" :key="index" :name="item.name"
							:disabled="item.disabled">
							{{item.name}}
						</u-radio>
					</u-radio-group>
				</view>
			</view>
			<view class="box-select-rules">
				若不接受自动调座，存在一定出票失败的概率
			</view>
		</view>
		<view class="box-select">
			<view class="box-select-radio">
				<u-form-item label="手机号码" height="42" label-width="254">
					<u-input v-model="form.name" placeholder="请输入您的常用手机号码" />
				</u-form-item>
			</view>
			<view class="box-select-rules phone-rules">
				手机号仅用于出票异常联系，取票码不会通过
			</view>
		</view>
		<view class="box-type">
			<view class="">
				选择购票方式
				<u-radio-group v-model="value" @change="radioGroupChange" style="margin-left: 154rpx;">
					<u-radio @change="radioChange" v-for="(item, index) in list" :key="index" :name="item.name"
						:disabled="item.disabled">
						{{item.name}}
					</u-radio>
				</u-radio-group>
			</view>
		</view>
		<view class="box-buy-type">
			微信支付
		</view>
		<view class="box-select box-rules">
			<view class="box-select-radio">
				<view class="">
					购票须知
					<u-radio-group v-model="value" @change="radioGroupChange" style="margin-left: 154rpx;">
						<u-radio @change="radioChange" v-for="(item, index) in list" :key="index" :name="item.name"
							:disabled="item.disabled">
							{{item.name}}
						</u-radio>
					</u-radio-group>
				</view>
			</view>
			<view class="box-select-rules">
				<span>1. 影院需实名登记观众信息，以及体温测</span><br>
				<span>2. 特价电影票，购买成功后将 <span class="warn-color">【不可退款、改签】</span>。支付前务必确认影院、影片、场次准确无误。
</span><br>
				<span>3. 支付完成后,特惠购票<span class="warn-color">【15~45分钟】</span>完成出票，快速购票【15分钟内】完成出票，若无法等待，请勿下单购买。
</span><br>
				<span>4. 若不能出票或者所选座位已售且不接受座位调整，订单将会<span class="warn-color">【24小时】</span>内自动退款。
</span><br>
				<span>5. 取票信息可在我的订单中查看
</span><br>
				<span>6. 出票成功后，在所选影院的自助取票或者前台取票即可。若无法取票，您可在订单页查看原图重新尝试取票。还是无效，您可申请售后或联系客服处理。</span>
				<br><span>7.如有疑问，请联系平台客服。</span>
			</view>
		</view>
		<view class="box-ticket-bottom">
			<span class="bottom-1">实际支付：</span>
			<span class="bottom-2">¥30.96 </span>
			<span class="bottom-3">共省：¥5.04</span>
			<view @click="handleClickByTicket">
				立即支付
			</view>
		</view>
		<view>
			<u-modal :title="title" :confirm-text="confirmText" v-model="show" :content="content" @confirm="handleConfirm"></u-modal>
			<u-modal :title="titles" :confirm-text="confirmTexts" v-model="shows" :content="contents" @confirm="handleConfirms"></u-modal>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				confirmText: '我知道啦',
				title: "自动调座规则",
				show: false,
				content: '第三方服务商出票，由于出票过程存在时间差，可能存在已选座位被占情况。为了不耽误您的时间，我们将按照优先选取从(银幕中央-核心区域-边缘)的顺序为您调换座位。购买多张票时将继续为您保持连座。',
				confirmTexts: '支付',
				titles: "温馨提示",
				shows: false,
				contents: '购 票 模 式：特惠购票',
				
				form: {
					name: ''

				},
				type: "text",
				list: [{
						name: '可调座',
						disabled: false
					},
					{
						name: '不可调座',
						disabled: false
					},

				],
				// u-radio-group的v-model绑定的值如果设置为某个radio的name，就会被默认选中
				value: '可调座',
			};
		},
		onLoad() {
			this.show = true;
		},
		methods: {
			handleClickByTicket() {
				this.shows = true;
			},
			handleConfirm() {
		this.show = false;
			},
			handleConfirms() {
			this.shows = false;
				},
			// 选中某个单选框时，由radio时触发
			radioChange(e) {
				// console.log(e);
			},
			// 选中任一radio时，由radio-group触发
			radioGroupChange(e) {
				// console.log(e);
			}
		}
	};
</script>

<style lang="scss" scoped>
	page {
		height: 100%;
		background-color: #F9FAFB;
	}

	.box {
		.box-info {
			padding: 0 20rpx 0rpx;

			.box-info-top {
				background: white;
				padding-top: 26rpx;
				padding-bottom: 38rpx;
				border-bottom: 2px dashed #E8E8E8;
				display: flex;

				.info-let {
					margin: 0 20rpx;
					width: 144rpx;
					height: 204rpx;
					background: #D8D8D8;
					border-radius: 8px;
					background: url(../../static/movie.png) no-repeat;
				}

				.info-right {
					.info-name {
						height: 42rpx;
						font-size: 30rpx;
						font-family: PingFangSC-Medium, PingFang SC;
						font-weight: 500;
						color: #333333;
						line-height: 42rpx;
						margin: 12rpx 0 6rpx;
					}

					.info-date {
						height: 34rpx;
						font-size: 24rpx;
						font-family: PingFangSC-Regular, PingFang SC;
						font-weight: 400;
						color: #3D8AF1;
						line-height: 34rpx;
					}

					.info-place {
						margin: 14rpx 0 6rpx;
						height: 34rpx;
						font-size: 24rpx;
						font-family: PingFangSC-Regular, PingFang SC;
						font-weight: 400;
						color: #666666;
						line-height: 34rpx;
					}

					.info-land {
						height: 34rpx;
						font-size: 24rpx;
						font-family: PingFangSC-Regular, PingFang SC;
						font-weight: 400;
						color: #666666;
						line-height: 34rpx;

						& sapn {
							margin-left: 20rpx;
						}
					}
				}
			}

			.box-info-rules {
				background: white;
				height: 66rpx;
				font-size: 24rpx;
				font-family: PingFangSC-Regular, PingFang SC;
				font-weight: 400;
				color: #333333;
				line-height: 66rpx;
				display: flex;

				& span {
					display: inline-block;
				}

				.rules-1 {
					width: 192rpx;
				}

				.rules-2 {
					width: 278rpx;
				}

				.rules-3 {
					width: 240rpx;
				}
			}
		}

		.box-select {
			width: 710rpx;
			height: 142rpx;
			background: #FFFFFF;
			border-radius: 8rpx;
			margin: 20rpx auto;

			.box-select-radio {
				width: 670rpx;
				height: 72rpx;
				line-height: 72rpx;
				border-bottom: 2rpx solid #E8E8E8;
				margin-left: 20rpx;
			}

			.box-select-rules {
				height: 68rpx;
				font-size: 24rpx;
				font-family: PingFangSC-Regular, PingFang SC;
				font-weight: 400;
				color: #3D8AF1;
				line-height: 68rpx;
				margin-left: 18rpx;
			}

			.phone-rules {
				color: #999999;
			}
		}
	.box-type{
		width: 710rpx;
		height: 288rpx;
		background: #FFFFFF;
		border-radius: 8rpx;
		margin: 20rpx auto;
	}
	.box-buy-type{
		margin: 0 auto 20rpx;
		width: 710rpx;
		height: 62rpx;
		background: #FFFFFF;
		border-radius: 8rpx;
		line-height: 62rpx;
	}
	.box-rules{
		height: 708rpx;
		.box-select-rules{
			height: 632rpx;
			font-size: 24rpx;
			font-family: PingFangSC-Regular, PingFang SC;
			font-weight: 400;
			color: #666666;
			line-height: 50rpx;
			.warn-color{
				color: #FB5F73;
			}
		}
	}
	.box-ticket-bottom{
		line-height: 80rpx;
		position: relative;
		width: 750rpx;
		height: 80rpx;
		background: #FFFFFF;
		box-shadow: 0rpx -4rpx 8rpx 0rpx rgba(251, 95, 115, 0.06);
	.bottom-1{
		margin-left: 20rpx;
		font-size: 30rpx;
		font-family: PingFangSC-Regular, PingFang SC;
		font-weight: 400;
		color: #666666;
	}
	.bottom-2{
		font-size: 30rpx;
		font-family: PingFangSC-Regular, PingFang SC;
		font-weight: 400;
		color: #FB5F73;
	}
	.bottom-3{
		margin-left: 28rpx;
		color: #3D8AF1;
		font-size: 24rpx;
	}
	& view{
		position: absolute;
		width: 156rpx;
		height: 52rpx;
		background: #FB5F73;
		border-radius: 38rpx;
		line-height: 52rpx;
		text-align: center;
		top: 14rpx;
		right: 14rpx;
		font-size: 30rpx;
		font-family: PingFangSC-Regular, PingFang SC;
		font-weight: 400;
		color: #FFFFFF;
	}
	}
	}
</style>
