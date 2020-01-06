<template>
	<view class="root_wapper">
		<image :src="user_icon_img" :style="{width:user_icon_width+'rpx',height:user_icon_height+'rpx'}" style="border-radius: 100%;"></image>
		<view class="vip_wapper">
			<image v-if="vip_img_url == '1'" src="https://addressbook-1300413889.cos.ap-shanghai.myqcloud.com/common/v/v-y.png" :style="{width:vip_icon_width+'rpx',height:vip_icon_height+'rpx'}"></image>
			<image v-if="vip_img_url == '2'" src="https://addressbook-1300413889.cos.ap-shanghai.myqcloud.com/common/v/v-r.png" :style="{width:vip_icon_width+'rpx',height:vip_icon_height+'rpx'}"></image>
			<image v-if="vip_img_url == '4'" src="https://addressbook-1300413889.cos.ap-shanghai.myqcloud.com/common/v/v-b.png" :style="{width:vip_icon_width+'rpx',height:vip_icon_height+'rpx'}"></image>
			<image v-if="vip_img_url == '3'" src="https://addressbook-1300413889.cos.ap-shanghai.myqcloud.com/common/v/v-g.png" :style="{width:vip_icon_width+'rpx',height:vip_icon_height+'rpx'}"></image>
		</view>
	</view>
</template>

<script>
	export default{
		name:'lilaiIcon' ,
		props:{
			vip_url:{
				type:String ,
				default:''
			},
			vip_width:{
				type:Number,
				default:35
			},
			vip_height:{
				type:Number,
				default:35
			},
			user_icon:{
				type:String ,
				default:''
			},
			icon_width:{
				type:Number,
				default:96
			},
			icon_height:{
				type:Number,
				default:96
			}
		},
		data(){
			return {
				vip_img_url:'',
				vip_icon_width:35,
				vip_icon_height:35,
				user_icon_img:'',
				user_icon_width:96,
				user_icon_height:96
			}
		},
		created() {
			this.vip_img_url = this.vip_url ;
			this.user_icon_img = this.user_icon ;
			this.user_icon_width = this.icon_width ;
			this.user_icon_height = this.icon_height ;
			this.vip_icon_width = this.vip_width ;
			this.vip_icon_height = this.vip_height ;
		} ,
		methods:{
			
		}
	}
</script>

<style>
	.root_wapper{
		padding: 0;
		position: relative;
		display: flex;
	}
	.vip_wapper{
		padding: 0;
		position: absolute;
		bottom: 2rpx;
		right: 2rpx;
		display: flex;
		background-color: white;
		border-radius: 100%;

	}
	.vip_wapper image{z-index: 101;}
</style>
