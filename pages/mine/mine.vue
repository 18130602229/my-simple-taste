<template>
	<view>
		<nav-bar backState="2000" title="我的"></nav-bar>
		<!-- 公共组件-每个页面必须引入 -->
		<public-module></public-module>
        <view>
			<view class="head-info">
				<image src="../../static/demo/1.jpg"></image> 
				<view>
					<view>上官菲</view>
					<view>南山区西丽街道留仙茗苑</view>
				</view>
				<image src="../../static/demo/icon_right.png"></image>
			</view>
		</view>
		<view class="mine-data">
			<view><text>教授</text><text>(2)</text></view>
			<view><text>学习</text><text>(3)</text></view>
		</view>
		<view>
			<view class="nav_list" @click="onPageJump('/pages/demo/formDemo')">
				<image src="../../static/demo/icon_case.png" mode="aspectFit"></image>
				<text>账号金额</text>
			</view>
			<view class="nav_list" @click="onPageJump('/pages/demo/formDemo')">
				<image src="../../static/demo/icon_case.png" mode="aspectFit"></image>
				<text>信用积分</text>
			</view>
			<view class="nav_list" @click="onPageJump('/pages/demo/formDemo')">
				<image src="../../static/demo/icon_case.png" mode="aspectFit"></image>
				<text>意见反馈</text>
			</view>
		</view>
		<z-navigation></z-navigation>
	</view>
</template>

<script>
import zNavigation from '@/components/module/navigation.vue';
export default {
	components: {
		zNavigation
	},
	data() {
		return {};
	},
	//第一次加载
	onLoad(e) {
		// 隐藏原生的tabbar
		uni.hideTabBar();
	},
	//页面显示
	onShow() {
		// 隐藏原生的tabbar
		uni.hideTabBar();
	},
	//方法
	methods: {
		onPageJump(url) {
			uni.navigateTo({
				url: url
			});
		}
	},
	//页面隐藏
	onHide() {},
	//页面卸载
	onUnload() {},
	//页面下来刷新
	onPullDownRefresh() {},
	//页面上拉触底
	onReachBottom() {},
	//用户点击分享
	onShareAppMessage(e) {
		return this.wxShare();
	}
};
</script>
<style lang="scss" scoped>
@import '@/style/mixin.scss';
.mine-data{
	margin-top: 10rpx;
	display: flex;
	view{
		color: #f00;
		width: 33%;
		border: 1rpx;
		text-align: center;
		border: 1px solid;
	}
}
.head-info{
	background-color: #fff;
	display: flex;
	image{
		border-radius:50%;
		width: 200rpx;
		height: 200rpx;
	}
}
.nav_list {
	background-color: #fff;
	padding: 30upx;
	display: flex;
	align-items: center;
	position: relative;
	margin-bottom: 10upx;
	&:active {
		background-color: #f5f5f5;
	}
	image {
		width: 40upx;
		height: 40upx;
	}
	text {
		font-size: 28upx;
		color: #333;
		margin-left: 30upx;
	}
	&::after {
		content: '';
		position: absolute;
		right: 30upx;
		top: 50%;
		transform: translateY(-50%);
		width: 40upx;
		height: 40upx;
		background-image: url('../../static/demo/icon_right.png');
		background-position: center center;
		background-repeat: no-repeat;
		background-size: cover;
	}
}
</style>
