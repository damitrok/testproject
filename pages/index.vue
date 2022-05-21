<template>
  <div class="conteiner">
    <AddProduct/>
    <ProductList/>
  </div>
  
</template>

<script>
import AddProduct from "../components/addProduct.vue";
import ProductList from '../components/productList.vue';

export default {
  
   name: 'addProduct',
    components: {
        AddProduct,
        ProductList
    }
}
</script>

<style>
html{
    font-size: 16px;
}
body{
    margin: 0;
    font-family: 'Source Sans Pro', sans-serif;
    color: #3F3F3F;
    background-color: #E5E5E5;
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