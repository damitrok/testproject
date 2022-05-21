<template>
    <div>
        <select name="" id="" class="selectSort"> 
            <option value="">По умолчанию</option>
            <option value="">Максимальная цена</option>
            <option value="">Минимальная цена</option>
            <option value="">По названию</option>
        </select>
        <div class="productList">
            <div v-for="product in products" :key="product.name" class="productList-element">
                <img :src="imgPath(product.img)" alt="" class="img">
                <div class="name">{{product.name}}</div>
                <div class="description">{{product.description}}</div>
                <div class="price">{{product.price}} руб.</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'productList',

    props: {
        products:{
            type:Array,
            require:true
        }
    },
    methods:{
        imgPath(p){
            return require(p);
        }
    },
    data(){
        return{
            products: []
                
        }
    }
}
</script>

<style lang="scss" scoped>
div{

    
    .selectSort{
        position: relative;
        left: 1245px;
        width: 120px;
        height: 36px;
        background: #FFFEFB;
        box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
        border-radius: 4px;
        border: none;
        font-weight: 400;
        font-size: 12px;
        line-height: 15px;
        color: #B4B4B4;
        margin-bottom: 9px;
        
    }
    .productList{
        margin-left: 340px;
        display: flex;
        flex-wrap: wrap;
        

        &-element{
            box-sizing: border-box;
            width: 332px;
            height: 423px;
            background-color: #FFFEFB;
            box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);  
            border-radius: 4px;
            margin: 6px;
            position: relative;


            .img{
                display: block;
                width: 100%;
                height: auto;
            }
            .name{
                margin: 16px;
                color: #3F3F3F;
                font-weight: 600;
                font-size: 20px;
                line-height: 25px;
            }

            .description{
                margin:0 16px 0 16px;
                font-weight: 400;
                font-size: 16px;
                line-height: 20px;
                color: #3F3F3F;
            }

            .price{
                margin: 0 16px 0 16px;
                font-weight: 600;
                font-size: 24px;
                line-height: 30px;
                color: #3F3F3F;
                position: absolute;
                bottom: 24px;
            }
        }
    }
}

</style>