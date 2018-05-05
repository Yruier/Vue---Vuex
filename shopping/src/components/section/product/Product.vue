<template>
    <div class="product">
    	<div class="list">
    		<Things id="1" :price="2" :sprice="dataInfo" @changePrice='getPrice'></Things>
	        <Things id="2" :price="3" :sprice="dataInfo" @changePrice='getPrice'></Things>
	        <Things id="3" :price="4" :sprice="dataInfo" @changePrice='getPrice'></Things>
	        <Things id="4" :price="5" :sprice="dataInfo" @changePrice='getPrice'></Things>
    	</div>
        <div class="payMent">
        	<p><span>余额不足￥100.00</span><b><em></em></b></p>
        	<p><span>奖金支付￥100.00</span><b><em></em></b></p>
        	<p><span>其他支付方式</span><span><i class="icon iconfont icon-angle-right"></i></span></p>
        </div>
    </div>
</template>
<script>

import Things from '../things/Things.vue';

    export default {
        data () {
        	return {
				totalPrice: {},
				dataInfo:{},
				allPrice:0
        	}
		},
		components: {
            Things
		},
        methods: {
			getPrice(data){
				this.dataInfo=data;
				if(data.type==='add'){
					this.allPrice += data.price
				}else{
					this.allPrice -= data.price
				}
				this.bus.$emit('updataPrice', this.allPrice);
				console.log(this.allPrice,'=',data.count,data.price,'dataInfo=====')
			}
        }
    }
</script>
<style lang="" scoped>
    .product {
    	margin-top: 10px;
    }
    
    .payMent {
    	background: #fff;
    	display: flex;
    	flex-direction: column;
    	padding: 7px 5px;
    }
    
    .payMent p {
    	display: flex;
    	justify-content: space-between;
    	
    }
</style>