<template>
  <div class="conteiner">
    <AddProduct @submitForm="addProduct" />
    <ProductList :products="list"/>
  </div>
  
</template>

<script>
import AddProduct from "../components/addProduct.vue";
import ProductList from '../components/productList.vue';
import list from '../static/list.json';

export default {
  
   name: 'addProduct',
   data() {
     return {
       list
     }
   },
   methods: {
     addProduct(prod) {
       this.list.push(prod);
     }
   },
    components: {
        AddProduct,
        ProductList
    }
}
</script>

<style  lang="scss" scoped>

html{
    font-size: 16px;
}
body{
    margin: 0;
    font-family: 'Source Sans Pro', sans-serif;
    color: #3F3F3F;
    background-color: #e5e5e5;
}

h1,h2,h3,h4,h5,h6{
    margin: 0;
}


*,
*:before,
*:after{
    box-sizing: border-box;
}

.conteiner{
    width: 1376px;
    margin: 32px 20px 0 32px; 
    display: flex;
}

</style>