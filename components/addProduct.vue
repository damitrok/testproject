<template>
  <div class="addProduct">
            <div class="header">Добавление товара</div>
            <div class="form">
                <div class="form-element">
                    <div class="headline ">Наименование товара<div class="required" ></div></div>
                    <input type="text" class="entryField" id="name" v-model="name" name="name" placeholder="Введите наименование товара" >
                    <p v-if="!name">Это поле обязательно</p>
                </div>
                <div class="form-element">
                    <div class="headline ">Описание товара</div>
                    <textarea name="" id="description" cols="30" rows="10" class="entryField -big" v-model="description" placeholder="Введите описание товара"></textarea>
                </div>
                <div class="form-element"> 
                    <div class="headline ">Ссылка на изображение товара<div class="required"></div></div>
                    <input type="text"  class="entryField" id="img" v-model="img" name="img" placeholder="Введите ссылку">
                    <p v-if="!img">Это поле обязательно</p>
                </div>
                <div class="form-element">
                    <div class="headline">Цена товара<div class="required"></div></div>
                    <input type="text"  class="entryField" id="price" v-model="price" name="price" placeholder="Введите цену">
                    <p v-if="!price">Это поле обязательно</p>
                </div>
                <button @click='addProduct' :class="['btn', {'active': submitBtnState}]" :disabled="!submitBtnState" type="submit" id="btn" >Добавить товар</button>
            </div>
            
        </div>
</template>

<script>
export default {
    data() {
        return{
            name: null ,
            description: null,
            img: null,
            price: null
        }
        
    },
    computed: {
        submitBtnState() {
            return (this.price && this.img && this.name);
        }
    },
    methods: {
        
        addProduct(){
            this.$emit('submitForm', {
                name: this.name,
                description: this.description,
                img: this.img,
                price: this.price
            })

            
        }

    }
}

</script>

<style lang="scss" scoped>

.addProduct{
    position: fixed;
    
    .header{
      
        font-size: 28px;
        font-weight: 600;
    }

    .form{
        margin-top: 16px;
        margin-right: 8px;
        background-color: #FFFEFB;
        box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
        border-radius: 4px;
        padding: 24px;
        width: 332px;
        min-height: 440px;

        &-element{

            margin-bottom: 16px;
            position: relative;

            p{
                font-weight: 400;
                font-size: 8px;
                line-height: 10px;
                letter-spacing: -0.02em;
                color: #FF8484;
            }
            .required{
                content:"";
                width: 4px;
                height: 4px;
                border-radius: 4px;
                background-color: #FF8484;
                display: inline-block;
                margin: 0 0 3px 0; 
            }
            .headline{
                font-size: 10px;
                font-weight: 400;
                color: #49485E;
                margin-bottom: 4px;
            }


            .entryField{
                width: 284px;
                height: 36px;
                background-color: #FFFEFB;
                border-radius: 4px;
                box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
                border: none;
                padding: 10px 0 11px 16px;
                
                &::placeholder {
                    color: #B4B4B4;
                    font-size: 12px;
                
                }
                &.-big{
                    width: 284px;
                    height: 108px;
                    padding: 10px 0 83px 16px;
                    overflow: hidden;
                    resize: none;
                }
            }


        }

        .btn{
            margin: 8px 0;
            width: 284px;
            height: 36px;
            border-radius: 10px;
            border: none;
            color: #B4B4B4;
            font-size: 12px;
            font-weight: 600px;
            font-family: 'Inter';
            background-color: #EEEEEE;

            
        }

        .active{
                background-color: #7BAE73;
                color: #FFFFFF;
                cursor: pointer;
         }
    }

}



</style>>

