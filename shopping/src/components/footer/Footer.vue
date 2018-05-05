<template>
	<div class="myFooter">
		<div class="footer">
			<div class="price">
				<span>总计</span><em >{{allPrice}}</em>
				<p>（含运费）</p>
			</div>
			<button>提交订单</button>
		</div>
	</div>
</template>
<script>

	export default {
		data(){
			return {
				allPrice:0
			}
		},
		created(){
			this.bus.$on('updataPrice', price => { 
				this.allPrice = price;
			});
		},
		beforeDestroy(){
			this.bus.$off('updataPrice')
		}
		
	}
</script>

<style type="text/css">
	.myFooter,.footer {
		width: 100%;
		height: 50px;
	}
	
	.footer {
		display: flex;
		align-items: center;
	}
	
	.footer button {
		height: 50px;
		flex: 3;
		background: #FC4141;
		border: 0;
		color: #fff;
		font-size: 16px;
	}
	
	.footer .price {
		flex: 7;
		text-align: right;
		margin-right: 20px;
	}
	
	.footer .price span, .footer .price em{
		color: #F71919;
	}
	
	.footer .price p {
		color: #666666;
	}
</style>