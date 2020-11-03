<template>
  <div>
	  <h1>Product List</h1>
	  <ul>
		  <li v-for="product in products" :key="product.id">{{product.title}} - {{product.price}} - {{product.inventory}}</li>
	  </ul>
  </div>
</template>

<script>
import shop from '@/api/shop'
import store from '@/store/index'
export default {
	computed:{
		products(){
			return store.state.products
		}
	},
	created(){
		shop.getProducts(products =>{
			store.state.products = products
		})
	}

}
</script>

<style>

</style>