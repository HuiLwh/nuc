<template>
	<view class="content">
		<!-- h5 -->
		<view class="nav_h5" v-if="h5">
			<span class="title_h5">慕课网</span>
		</view>
		<!-- 小程序 -->
		<view class="wx" v-else>
		   <!-- 解决元素占用手机上方的空间的 -->
		    <view class="block">
			</view>
		    <view class="nav">
				<text class="title">慕课网</text>
		    </view>
		</view>
		
		<view class="tab">
			<u-tabs 
			 :list="list" 
			 @click="click" class="w" 
			 :scrollable="false">
			 </u-tabs>
		</view>
		<view class="view">
			<Home v-if="index==0"></Home>
			<MF v-if="index==1"></MF>
			<SZ v-if="index==2"></SZ>
			<TY v-if="index==3"></TY>
		</view>
	</view>
</template>

<script>
	import Home from "@/components/Home/Home.vue"
	import MF from "@/components/MF/Mian.vue"
	import SZ from "@/components/SZ/ShiZ.vue"
	import TY from "@/components/TY/Ty.vue"
	export default {
		data() {
			return {
				h5:true,
				title:'Hello',
				marginheight:"100",
				list:[
					{name:'首页'},
					{name:'免费课'},
					{name:'实战课'},
					{name:'体系课'}
				],
				list1:[
					{name:'首页'},
					{name:'免费课'},
					{name:'实战课'},
					{name:'体系课'}
				],
				arrs:["Home","MF","SZ","TY"],
				iscomponent:"TY",
				home:false,
				new:false,
				Ty:true,
				index:0
			}
		},
		components:{
			Home,
			MF,
			SZ,
			TY
		},
		onLoad() {
			//#ifdef H5
			this.h5 = true
			//#endif
			//#ifndef H5
			this.h5 = false
			//#endif
		},
		methods: {
			click(item){
				console.log(item);
				this.index = item.index
			}
		}
	}
</script>

<style lang="scss">
	.content{
		background: #ededed;
		height: 100vh;
		.nav_h5{
			padding: 2% 0 0 20rpx;
			display: flex;
			align-items: center;
			.title_h5{
				margin: 0 0 0 20rpx;
				font-weight: 600;
			}
		}
		.wx{
			.block{
				height: var(--status-bar-height);
				width: 100%;
			}
			.nav{
				padding: 1% 0 0 20rpx;
				display: flex;
				align-items: center;
				.title{
					margin: 0 0 0 20rpx;
					font-weight: 700;
				}
			}
		}
	}
</style>
