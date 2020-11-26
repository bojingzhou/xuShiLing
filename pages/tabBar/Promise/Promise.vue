<template>
	<div>
		<div v-for="(item,index) in promise" :key="index">
			<uni-section :title="item.type" type="line"></uni-section>
			<view class="example-body">
				<uni-card :isShadow="true" :title="item.title" :subTitle="item.subTitle" mode="title" thumbnail="https://img-cdn-qiniu.dcloud.net.cn/new-page/uni.png" extra="" note="true" @click="clickCard">
					<view>
						<view class="image-box">
							<image class="image" mode="aspectFill" src="https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/shuijiao.jpg" />
						</view>
						<view class="content-box">
							<text class="content-box-text">{{item.content}}</text>
						</view>
					</view>
					<template slot="footer">
						<view class="footer-box">
							<view @click.stop="footerClick(item.id,0)"><text class="footer-box__item">喜欢</text></view>
							<view @click.stop="footerClick(item.id,1)"><text class="footer-box__item">评论</text></view>
						</view>
					</template>
				</uni-card>
			</view>
		</div>
		
	</div>
</template>

<script>
	export default {
		data() {
			return {
				promise:[
					{type:"姻缘",title:"姻缘标题",subTitle:"姻缘子标题",content:"姻缘内容",id:1},
					{type:"全家福",title:"全家福标题",subTitle:"全家福子标题",content:"全家福内容",id:1},
					{type:"财运",title:"财运标题",subTitle:"财运子标题",content:"财运内容",id:1},
				]
			}
		}
	}
</script>

<style>
	.image-box {
		/* #ifndef APP-NVUE */
		display: flex;
		flex-direction: column;
		/* #endif */
		height: 350rpx;
		overflow: hidden;
	}
	.image {
		/* #ifndef APP-NVUE */
		width: 100%;
		height: 100%;
		/* #endif */
		flex: 1;
	}
	.content-box {
		padding-top: 20rpx;
	}
	
	.content-box-text {
		font-size: 12px;
		line-height: 22px;
	}
	.footer-box {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		justify-content: space-between;
		flex-direction: row;
	}
	
	.footer-box__item {
		align-items: center;
		padding: 2px 0;
		font-size: 12px;
		color: #666;
	}
</style>
