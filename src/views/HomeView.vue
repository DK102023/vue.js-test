<template>
  <section class="banner">
    <div class="container">
      <div class="banner-item">
        <h1 class="banner-item--title">Онлайн-сервис доставки еды на дом</h1>
        <p class="banner-item--subtitle">
          Блюда из любимого ресторана привезет курьер в перчатках, маске и с
          антисептиком
        </p>
      </div>
    </div>
  </section>
  <section class="products">
    <div class="container">
      <div class="products-header">
        <h3 class="products-header--title">Рестораны</h3>
        <input
          class="products-header--search"
          type="text"
          placeholder="Поиск блюд и ресторанов"
        />
      </div>
      <div class="products-wrapper" id="rests-container">
        <router-link
          :to="`./rest?id=${rest.id}`"
          class="products-card"
          v-for="rest in restArray"
          :key="rest.id"
        >
          <div class="products-card__image">
            <img :src="getUrl(rest.image)" alt="" />
          </div>
          <div class="products-card__description">
            <div class="products-card__description-row">
              <h4 class="products-card__description--title">
                {{ rest.title }}
              </h4>
              <div class="products-card__description--badge">
                {{ rest.time }} мин
              </div>
            </div>
            <div class="products-card__description-row">
              <div class="products-card__description-info">
                <div class="products-card__description-info--rating">
                  <img src="../assets/img/star.svg" alt="" />{{ rest.rating }}
                </div>
                <div class="products-card__description-info--price">
                  От {{ rest.price }} ₽
                </div>
                <div class="products-card__description-info--group">
                  {{ rest.type }}
                </div>
              </div>
            </div>
          </div>
        </router-link>
      </div>
    </div>
  </section>
</template>
<script setup>
import { restArray } from "../constants/rests";
const getUrl = (name) => {
  return new URL(`${name}`, import.meta.url);
  // return `..assets/img/rests/image-01.jpg`
};
</script>