

<template>
     <div class="cart-modal__overlay" :class="{open: isOpen}" @click.self="CloseModal()" >
        <div class="cart-modal">
            <div class="cart-modal__header">
                <h2 class="cart-modal__header--title">
                    Корзина
                </h2>
                <span class="cart-modal__header--close" id="close-button" @click="CloseModal()">
                    <svg xmlns="http://www.w3.org/2000/svg" width="26" height="26" viewBox="0 0 26 26" fill="none">
                        <path
                            d="M16.0035 13L25.3506 3.65245C25.6077 3.39513 25.7496 3.05184 25.75 2.68578C25.75 2.31952 25.6081 1.97582 25.3506 1.71891L24.5315 0.900011C24.274 0.642084 23.9307 0.500824 23.5642 0.500824C23.1984 0.500824 22.8551 0.642084 22.5976 0.900011L13.2504 10.247L3.90285 0.900011C3.64573 0.642084 3.30224 0.500824 2.93598 0.500824C2.57012 0.500824 2.22663 0.642084 1.96951 0.900011L1.15 1.71891C0.616667 2.25225 0.616667 3.11973 1.15 3.65245L10.4974 13L1.15 22.3472C0.892683 22.6049 0.751016 22.9482 0.751016 23.3142C0.751016 23.6803 0.892683 24.0236 1.15 24.2811L1.96931 25.1C2.22642 25.3577 2.57012 25.4992 2.93577 25.4992C3.30203 25.4992 3.64553 25.3577 3.90264 25.1L13.2502 15.7529L22.5974 25.1C22.8549 25.3577 23.1982 25.4992 23.564 25.4992H23.5644C23.9305 25.4992 24.2738 25.3577 24.5313 25.1L25.3504 24.2811C25.6075 24.0238 25.7494 23.6803 25.7494 23.3142C25.7494 22.9482 25.6075 22.6049 25.3504 22.3474L16.0035 13Z"
                            fill="black" />
                    </svg>
                </span>
            </div>
            <div class="cart-modal__body">
                <div class="cart-item">
                    <p class="cart-item__title">Ролл угорь стандарт</p>
                    <div class="cart-item__controls">
                        <div class="cart-item__controls--price">250 ₽</div>
                        <button class="btn btn-outline">-</button>
                        <div class="cart-item__controls--count">1</div>
                        <button class="btn btn-outline">+</button>
                    </div>
                </div>

                <div class="cart-item">
                    <p class="cart-item__title">Ролл угорь стандарт</p>
                    <div class="cart-item__controls">
                        <div class="cart-item__controls--price">250 ₽</div>
                        <button class="btn btn-outline">-</button>
                        <div class="cart-item__controls--count">1</div>
                        <button class="btn btn-outline">+</button>
                    </div>
                </div>

                <div class="cart-item">
                    <p class="cart-item__title">Ролл угорь стандарт</p>
                    <div class="cart-item__controls">
                        <div class="cart-item__controls--price">250 ₽</div>
                        <button class="btn btn-outline">-</button>
                        <div class="cart-item__controls--count">1</div>
                        <button class="btn btn-outline">+</button>
                    </div>
                </div>

            </div>
            <div class="cart_modal__footer">
                <div class="cart_modal__footer--price">1250 ₽</div>
                <div class="cart_modal__footer--controls">
                    <button class="btn btn-primary">Оформить заказ</button>
                    <button class="btn btn-outline">Отмена</button>
                </div>
            </div>
        </div>
    </div>
</template>
<script setup>
    const {isOpen} = defineProps({isOpen : Boolean})
    //console.log("isOpen="+isOpen);
     const emit = defineEmits(['toggleModal'])
        const CloseModal = () =>{
       emit('toggleModal') // передаем сообщение о срабатывании ф-ции в App.vue
    }
</script>
<style scoped>
    .cart-modal__overlay{
  background: rgba(0, 0, 0, 0.40);
  width: 100%;
  height: 100%;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  /*display: flex;*/
  align-items:center;
  justify-content: center;
  display: none;
}
.cart-modal__overlay.open{
  display: flex;
}
.cart-modal{
  max-width: 780px;
  width: 100%;
  padding: 40px 45px;
  border-radius: 5px;
  background:  #FFF;
}
.cart-modal__header{
  display: flex;
  align-items:center;
  justify-content: space-between;
  margin-bottom: 48px;
}
.cart-modal__header--title{
  color: #000;
  font-size: 36px;
  font-weight: 700;
  margin: 0;
}
.cart-modal__header--close{
  cursor: pointer;
}
.cart-item {
  display: flex;
  align-items:center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 10px;
  
}
.cart-item:not(:last-child){
  padding-bottom: 10px;
  margin-bottom: 10px;
  border-bottom: 1px solid #D9D9D9;
}
.cart-item__title{
  color: #000;
  font-size: 18px;
  font-weight: 400;
  line-height: 32px; 
  margin: 0;

}
.cart-item__controls--price{
  color: #000;
  font-size: 20px;
  font-weight: 700;
  line-height: 32px; 
  margin-right: 47px;
}
.cart-item__controls{
  display: flex;
  align-items:center;
  /*justify-content: space-between;*/
}
.cart-item__controls button{
  padding: 5px 16px;
  border-radius: 2px;
  border: 1px solid #40A9FF;
  background: #FFF;
  color:  #40A9FF;
}
.cart-item__controls--count{
  color: #000;
  text-align: center;
  font-size: 16px;
  font-weight: 400;
  line-height: 24px; 
  margin-left: 15px;
  margin-right: 15px;
}
.cart_modal__footer{
  display: flex;
  align-items:center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 15px;
  margin-top: 50px;
}
.cart_modal__footer--price {
  border-radius: 5px;
  background:  #262626;
  color: #FAFAFA;
  padding: 15px 20px;
  font-size: 20px;
  font-weight: 700;
  margin-right: 47px;
}
.cart_modal__footer--controls{
  display: flex;
  justify-content: flex-end;
  align-items:center;
  gap: 20px
}

</style>
