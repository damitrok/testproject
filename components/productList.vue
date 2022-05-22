<template>
    <div>
        <select name="" id="" class="selectSort"> 
            <option value="">По умолчанию</option>
            <option value="">Максимальная цена</option>
            <option value="">Минимальная цена</option>
            <option value="">По названию</option>
        </select>
        <div class="productList">
            
            <div v-for="(product, index) in products" :key="product.name"   class="productList-element">
                <div class="delete" @click='deleteProduct(index)'>
                    <img class="cart" src="~/static/delete.svg" alt="">
                </div>
                <div class="img-overlay">
                    <img :src="product.img" key="" alt="" class="img">
                </div>
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

        deleteProduct(id){
            
            this.products.splice(id, 1);
            

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

            &:hover{
                cursor: pointer;
                .delete{
                    position: absolute;
                    width: 32px;
                    height: 32px;
                    right: -10px;
                    top: -10px;
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    background: #FF8484;
                    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
                    border-radius: 10px;
                    
                
                    .cart{
                        width: 12px;
                        height: 16px;
                    }
                }
            }

            .delete{
                display: none;
            }
            
            .img-overlay {
                height: 200px;
                width: 332px;
                overflow: hidden;
                .img{
                    width: 100%;
                    height: auto;
                    object-fit: contain;
                    left: 50%;
                    top: 50%;
                }
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