<template>
	<view class="content">
		<view class="content_info">
			<view class="title">
				<span class="span1">全部</span>
				<span>零基础</span>
				<span>进阶课</span>
			</view>
			<view class="box_info">
				<view class="info">
					<u-image src="https://cdn.uviewui.com/uview/album/1.jpg"></u-image>
					<p>73人学习 新上好课</p>
					
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"Ty",
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	.content_info{
		.title{
			font-size: 32rpx;
			margin-left: 15rpx;
			span{
				margin-left: 9rpx;
			}
			.span1{font-weight: 700;}
		}
		.box_info{
			
		}
	}
</style>