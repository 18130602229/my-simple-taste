<template>
	<view>
		<nav-bar backState="2000" title="资源"></nav-bar>
		<!-- 公共组件-每个页面必须引入 -->
		<public-module></public-module>
		<view class="nav_list" @click="onPageJump('/pages/demo/formDemo')">
			<image src="../../static/demo/icon_case.png" mode="aspectFit"></image>
			<text>好友列表</text>
		</view>
		<view class="nav_list" @click="onPageJump('/pages/demo/formDemo')">
			<image src="../../static/demo/icon_case.png" mode="aspectFit"></image>
			<text>涉及领域</text>
		</view>
		<view class="nav_list" @click="onPageJump('/pages/demo/formDemo')">
			<image src="../../static/demo/icon_case.png" mode="aspectFit"></image>
			<text>自我总计</text>
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