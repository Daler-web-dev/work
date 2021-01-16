<template>
	<div class="product-item"> 
		<img src="../../public/images/10163-015_1.jpg">
		<div class="description">
			<span class="item-title">{{ productValue.title }}</span>
			<span>{{ productValue.price }}сум</span>
		</div>
		<button class="plus-minus-btn" v-if="productValue.isOnCart == false" @click="this.$emit('transferToCart', productValue.id)">Добавить в корзину</button>
		<button class="plus-minus-btn" v-else>
			<span class="plus-and-minus" @click="this.$emit('changeCount', {id: productValue.id, data: true})">+</span>
			<span class="num">{{productValue.quantity}}</span>
			<span class="plus-and-minus" @click="this.$emit('changeCount', {id: productValue.id, data: false})">-</span>
		</button>
	</div>
</template>

<script>
export default {
    name: 'catalogItem',
    props: [
		'productValue'
    ]
}
</script>

<style>
.product-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: white;
    height: 92px;
    width: 280px;
    padding: 10px;
	border-radius: 12px;
    border: 1px solid white;
	
}
.product-item:hover {
	border: 1px solid #9FD7E8;
    box-shadow: 5px 5px 10px grey;
}
.product-item img {
    width: 50px;
    height: 50px;
    margin: 0px 10px 0px 0px;
}
.product-item .description {
    display: flex;
	flex-direction: column;
}
.product-item .description .item-title {
	margin-top: 15px;
}
.plus-and-minus {
	padding: 12px;
	font-size: 20px;
}
.plus-and-minus:hover {
	color: #FF6D00;
}
</style>