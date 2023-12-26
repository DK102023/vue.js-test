<script setup>
import { goodsArray } from "../constants/goods";
const getUrl = (name) => {
  return new URL(`../assets/img/goods/${name}`, import.meta.url);
};
</script>

<template>
  <section class="products">
    <div class="container">
      <div class="products-wrapper" id="goods-container">
        <!--<div class="products-card">-->
        <router-link
          to="/"
          class="products-card"
          v-for="goods in goodsArray"
          :key="goods.id"
        >
          <div class="products-card__image">
            <img :src="getUrl(goods.image)" alt="" />
          </div>
          <div class="products-card__description">
            <div class="products-card__description-row">
              <h5 class="products-card__description--name">
                {{ goods.title }}
              </h5>
            </div>
            <div class="products-card__description-row">
              <p class="products-card__description--text">{{ goods.desc }}</p>
            </div>
            <div class="products-card__description-row">
              <div class="products-card__description-controls">
                <button class="btn btn-primary">
                  В корзину<i
                    class="fa fa-shopping-basket"
                    aria-hidden="true"
                  ></i>
                </button>
                <span class="products-card__description-controls--price"
                  >{{ goods.price }} ₽</span
                >
              </div>
            </div>
          </div>
        </router-link>
      </div>
    </div>
  </section>
</template>
