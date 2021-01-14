<template>
  <div class="product-item" @click="this.$emit('toCart', productValue.id)"> 
      <img src="../../public/images/alesia-kazantceva-XLm6-fPwK5Q-unsplash.png">
      <div class="description">
          <span>{{ productValue.title }}</span>
          <span>{{ productValue.price }}сум</span>
      </div>
      <i>{{ productValue.quantity }}</i>
  </div>
</template>

<script>
export default {
    name: 'productItem',
    props: [
        'productValue'
    ]
}
</script>

<style>
.product-item {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: white;
    height: 92px;
    width: 280px;
    padding: 10px;
    border-radius: 12px;
    cursor: pointer;
}
.product-item:hover {
    border: 1px solid blue;
}
.product-item img {
    width: 50px;
    height: 50px;
    margin-right: 30px;
}
.product-item .description {
    display: flex;
    flex-direction: column;
}
</style>