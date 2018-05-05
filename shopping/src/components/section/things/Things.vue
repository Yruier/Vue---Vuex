<template>
	<div class="thing">
		<p>
			<span><i class="icon iconfont icon-03"></i></span>
			<span>恒指然旗舰店</span>
		</p>
		<dl>
			<dt><img src="../../../assets/1.png" alt=""/></dt>
			<dd>
				<h5>阿萨德加班费大部分安静地发表爱上都很方便安理会的说法卢卡申科解放碑</h5>
				<h6>
                    <div class="left">
                        <span>￥<em>2.00</em></span>
                        <span style="text-decoration:line-through">￥<em>5.00</em></span>
                    </div>
                    <div class="right">
                        <span @click="changeNum('reduce')"><i class="icon iconfont icon-jian"></i></span>
                        <span>{{count}}</span>
                        <span @click="changeNum('add')"><i class="icon iconfont icon-jia"></i></span>
                    </div>
                </h6>
			</dd>
		</dl>
		<div class="price"> <span>商品总金额：</span><span>￥{{price}}</span></div>
		<div class="price"> <span>运费：</span><span>￥10.00</span></div>
		<div class="price"> <span>总额（含运费）：</span><span>￥{{allPrice}}</span></div>
	</div>
</template>
<script>
	export default {
		data() {
			return {
				count: 1,
				allPrice:0
			}
		},
		props: {
			id:{
				required: true,
				type: String
			},
			price: {
				required: true,
				type: Number
			},
			id: {
				required: true,
				type: String
			}
		},
		created(){
			this.allPrice=this.price * this.count;
			this.$emit('changePrice',{
				price:this.price,
				count:this.count,
				type:'add'
			});
		},
		methods: {
			changeNum:function(type) {
				type==='add'?this.count++:this.count--;
				if(this.count < 1) {
					this.count = 1;
					return;
				}
				this.allPrice=this.price * this.count
				this.$emit('changePrice',{
					price:this.price,
					count:this.count,
					type:type
				});
			}
		}
	}
</script>
<style lang="" scoped>
	* {
		box-sizing: border-box;
	}
	
	.thing {
		width: 100%;
		height: auto;
		padding: 10px;
		margin-bottom: 10px;
		border-bottom: 1px solid #ccc;
		background: #fff;
	}
	
	.thing p {
		width: 100%;
		height: auto;
		padding: 10px 0 10px 0;
	}
	
	.thing p span .icon {
		color: #FF6D1F;
		font-size: 18px;
	}
	
	.thing dl {
		width: 100%;
		display: flex;
	}
	
	.thing dl dt {
		width: 105px;
		height: 105px;
		border: 1px solid #ccc;
	}
	
	.thing dl dt img {
		width: 100%;
		height: auto;
	}
	
	.thing dl dd {
		flex: 1;
		padding-left: 10px;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}
	
	.thing dl dd h5 {
		display: -webkit-box;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		word-break: break all;
		overflow: hidden;
		text-overflow: ellipsis;
		font-weight: normal;
	}
	
	.thing dl dd h6 {
		display: flex;
		justify-content: space-between;
		padding-right: 10px;
	}
	
	.thing dl dd h6 .left {
		display: flex;
		flex: 1;
		flex-direction: column;
	}
	
	.thing dl dd h6 .right span {
		display: inline-block;
		width: 20px;
		height: 20px;
		text-align: center;
		line-height: 20px;
		border: 1px solid #ccc;
		vertical-align: middle;
	}
	
	.thing dl dd h6 .right span:nth-of-type(2) {
		font-size: 16px;
	}
	
	.thing .price {
		width: 100%;
		padding: 5px 0;
		display: flex;
		justify-content: space-between;
	}
	
	.thing .price span {
		color: #666666;
	}
	
	.thing .price:last-child span:last-child {
		color: #FC4141;
	}
</style>