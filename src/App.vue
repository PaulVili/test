<template >
  <TheHeader 
    isLiked="isLiked" 
    addProductToCart="addProductToCart" 
    counter="counter"
    class="header-position"
    :class="{ 'headerHidden': headerHidden === true }" />
  <div class="main">
    <div class="product-block-line">
      <div class="product-slider">
        <TheCarousel :cards="cards" class="carousel" />
      </div>
      <div class="product-block">
        <div class="product-block-heading">
          <h2>{{ productName }}</h2>
          <span>Арт. 02765/46</span>
        </div>
        <div class="comment-block">
          <p>Отзывы</p>
          <div class="stars">
            <svg width="10" height="10" viewBox="0 0 10 10" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M5 7.635L8.09 9.5L7.27 5.985L10 3.62L6.405 3.315L5 0L3.595 3.315L0 3.62L2.73 5.985L1.91 9.5L5 7.635Z"
                fill="#333333" />
            </svg>
            <svg width="10" height="10" viewBox="0 0 10 10" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M5 7.635L8.09 9.5L7.27 5.985L10 3.62L6.405 3.315L5 0L3.595 3.315L0 3.62L2.73 5.985L1.91 9.5L5 7.635Z"
                fill="#333333" />
            </svg>
            <svg width="10" height="10" viewBox="0 0 10 10" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M5 7.635L8.09 9.5L7.27 5.985L10 3.62L6.405 3.315L5 0L3.595 3.315L0 3.62L2.73 5.985L1.91 9.5L5 7.635Z"
                fill="#333333" />
            </svg>
            <svg width="10" height="10" viewBox="0 0 10 10" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M5 7.635L8.09 9.5L7.27 5.985L10 3.62L6.405 3.315L5 0L3.595 3.315L0 3.62L2.73 5.985L1.91 9.5L5 7.635Z"
                fill="#333333" />
            </svg>
            <svg width="10" height="10" viewBox="0 0 10 10" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M5 2.565L5.485 3.71L5.72 4.265L6.32 4.315L7.555 4.42L6.615 5.235L6.16 5.63L6.295 6.22L6.575 7.425L5.515 6.785L5 6.465L4.485 6.775L3.425 7.415L3.705 6.21L3.84 5.62L3.385 5.225L2.445 4.41L3.68 4.305L4.28 4.255L4.515 3.7L5 2.565ZM5 0L3.595 3.315L0 3.62L2.73 5.985L1.91 9.5L5 7.635L8.09 9.5L7.27 5.985L10 3.62L6.405 3.315L5 0Z"
                fill="#333333" />
            </svg>

          </div>
          <a href="#">
            14 отзывов
          </a>
          <svg width="10" height="15" viewBox="0 0 10 15" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M1 1L9 8L1 14.5" stroke="#333333" />
          </svg>
        </div>
        <div class="product-block-price">
          <p class="product-block-price-item">800 ₽</p>
          <p class="product-block-price-item-sale">1 500 ₽</p>
          <div>
            <svg width="10" height="15" viewBox="0 0 10 15" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M1 1L9 8L1 14.5" stroke="#333333" />
            </svg>
          </div>
        </div>
        <div class="product-block-sales">
          <p>скидка -36%</p>
          <p>акция -20%</p>
        </div>
        <div class="product-block-sizes">
          <select>
            <option selected="true" disabled="disabled"> Выбрать размер </option>
            <option value="S">S</option>
            <option value="M">M</option>
            <option value="L">L</option>
            <option value="XL">XL</option>
          </select>
          <a href="#">Определить размер</a>
        </div>
        <div class="product-block-amount">
          <div class="addToCart">
            <div class="counter">
              <p @click="counter++">+</p>
              <p>{{ counter }}</p>
              <p @click="minusCounter">-</p>
            </div>
            <div class="addToCart-line">
              <div class="addToCart-relative">
                <button @click="addToCart">Добавить в корзину</button>
                <p 
                  v-show="addToCartClicked"
                  class="addToCart-absolute"
                >Товар {{ productName }} в количестве {{ counter }} добавлен в корзину</p>
              </div>
              <div class="addToCart-relative">
                <div @click="like">
                  <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M11.9 7.0948C10.6998 1.47892 1.40881 5.90389 5.76037 11.6018C10.1119 17.2996 12.4 19.4908 12.4 19.4908"
                      stroke="white" />
                    <path d="M11.8941 7.0948C13.0944 1.47892 22.7304 5.90389 18.3789 11.6018C14.0273 17.2996 11.7 19.5 11.7 19.5"
                      stroke="white" />
                    <path d="M11.391 6.70752L12.4043 6.70757L12.3834 7.24079H11.391V6.70752Z" fill="white" />
                  </svg>
                </div>
                <p 
                  v-show="likeClicked"
                  class="likeClicked-absolute"
                >Товар {{ productName }} в количестве {{ counter }} добавлен в избранное</p>
              </div>
            </div>
          </div>
          <div>
            <a href="#">Купить в 1 клик</a>
          </div>
        </div>
        <div class="product-block-about">
          <a href="#">
            <div class="product-block-about-item">
              <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                <circle cx="10" cy="10" r="7" stroke="#333333" />
                <path d="M6 8C6.24928 8 8.75787 6.5 8.75787 6.5H10.0043H11.2507C11.2507 6.5 13.7507 8 14 8"
                  stroke="#333333" />
                <path d="M6.01577 7.39283L6.01576 9.17806L7.76075 9.4756L7.76075 13.9386" stroke="#333333" />
                <path d="M13.9842 7.39283L13.9842 9.17806L12.2393 9.4756L12.2478 13.9386" stroke="#333333" />
                <line x1="7.51145" y1="13.4385" x2="12.4971" y2="13.4385" stroke="#333333" />
                <path d="M8.50859 6.5C8.50859 6.5 9.00716 8.28522 10.0043 8.28522C11.0014 8.28522 11.5 6.5 11.5 6.5"
                  stroke="#333333" />
              </svg>
              <p>Описание товара</p>
            </div>
          </a>
          <a href="#">
            <div class="product-block-about-item">
              <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                <circle cx="10" cy="10" r="7" fill="white" stroke="#333333" />
                <path d="M9.55453 5.5L9.55453 10.7061L13.5 13" stroke="#333333" />
              </svg>
              <p>Доставка и возврат</p>
            </div>
          </a>
          <a href="#">
            <div class="product-block-about-item product-block-about-item-pay">
              <svg width="14" height="10" viewBox="0 0 14 10" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="0.5" y="0.5" width="13" height="9" rx="0.5" stroke="#333333" />
                <rect x="1" y="3" width="12" height="2" fill="#333333" />
              </svg>
              <p class="product-block-about-item-pay">Способы оплаты</p>
            </div>
          </a>
        </div>
      </div>
    </div>
    <div class="see-all-styles">
      <a href="#">Посмотреть все стили</a>
    </div>
    <div class="photos-block">
      <div class="photos-block-items photos-block-item-big-block" v-on:mouseenter="photosBlockItem1 = true"
        v-on:mouseleave="photosBlockItem1 = false">
        <div class="photos-block-item" v-show="photosBlockItem1">
          <div class="photos-block-item-full-screen">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <rect x="4.5" y="6.5" width="13" height="13" rx="1.5" stroke="white" />
              <path
                d="M6.33784 6.63126L6.33784 6.49958C6.33784 5.39501 7.23327 4.49958 8.33784 4.49958L17.5 4.49959C18.6045 4.49959 19.5 5.39502 19.5 6.49959L19.5 15.9382C19.5 16.9853 18.5159 17.7537 17.5 17.4997V17.4997"
                stroke="white" />
            </svg>
          </div>
          <div class="photos-block-item-product">
            <svg width="48" height="48" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M11.2445 14.2998H36.7555C38.2133 14.2998 39.3618 15.542 39.2478 16.9953L37.5851 38.1953C37.4831 39.4962 36.3976 40.4998 35.0927 40.4998H12.9073C11.6024 40.4998 10.5169 39.4962 10.4149 38.1953L8.75216 16.9953C8.63818 15.542 9.78674 14.2998 11.2445 14.2998Z"
                stroke="white" />
              <path d="M15.004 24.4857C15.004 24.4857 14.5437 7 23.5 7C32.4563 7 31.996 24.4857 31.996 24.4857"
                stroke="white" />
            </svg>
          </div>
          <p class="photos-block-item-paragraph">Узнай, что на мне</p>
          <div class="photos-block-item-likes">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M12.4287 7.25725L13.7612 5.03654L17.1965 5.46595L18.5 7.63849V10.3206L12.0145 18.1959L5.93878 10.2507L5.05633 8.04458L6.34555 5.89588L9.35443 4.60636L11.6159 7.32009L12.0665 7.86089L12.4287 7.25725Z"
                fill="white" stroke="white" />
              <path
                d="M11.9 7.0948C10.6998 1.47892 1.40879 5.90389 5.76035 11.6018C10.1119 17.2996 12.4 19.4908 12.4 19.4908"
                stroke="white" />
              <path
                d="M11.8941 7.0948C13.0943 1.47892 22.7304 5.90389 18.3788 11.6018C14.0273 17.2996 11.7 19.5 11.7 19.5"
                stroke="white" />
              <path d="M11.391 6.70752L12.4043 6.70757L12.3834 7.24079H11.391V6.70752Z" fill="white" />
            </svg>
            <p>200</p>
          </div>

        </div>
      </div>
      <div class="photos-blocks-line">
        <div class="photos-block-line">
          <div class="photos-block-items photos-block-item-2" v-on:mouseenter="photosBlockItem2 = true"
            v-on:mouseleave="photosBlockItem2 = false">
            <div class="photos-block-item " v-show="photosBlockItem2">
              <div class="photos-block-item-full-screen">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <rect x="4.5" y="6.5" width="13" height="13" rx="1.5" stroke="white" />
                  <path
                    d="M6.33784 6.63126L6.33784 6.49958C6.33784 5.39501 7.23327 4.49958 8.33784 4.49958L17.5 4.49959C18.6045 4.49959 19.5 5.39502 19.5 6.49959L19.5 15.9382C19.5 16.9853 18.5159 17.7537 17.5 17.4997V17.4997"
                    stroke="white" />
                </svg>
              </div>
              <div class="photos-block-item-product">
                <svg width="48" height="48" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M11.2445 14.2998H36.7555C38.2133 14.2998 39.3618 15.542 39.2478 16.9953L37.5851 38.1953C37.4831 39.4962 36.3976 40.4998 35.0927 40.4998H12.9073C11.6024 40.4998 10.5169 39.4962 10.4149 38.1953L8.75216 16.9953C8.63818 15.542 9.78674 14.2998 11.2445 14.2998Z"
                    stroke="white" />
                  <path d="M15.004 24.4857C15.004 24.4857 14.5437 7 23.5 7C32.4563 7 31.996 24.4857 31.996 24.4857"
                    stroke="white" />
                </svg>
              </div>
              <p class="photos-block-item-paragraph">Узнай, что на мне</p>
              <div class="photos-block-item-likes">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M12.4287 7.25725L13.7612 5.03654L17.1965 5.46595L18.5 7.63849V10.3206L12.0145 18.1959L5.93878 10.2507L5.05633 8.04458L6.34555 5.89588L9.35443 4.60636L11.6159 7.32009L12.0665 7.86089L12.4287 7.25725Z"
                    fill="white" stroke="white" />
                  <path
                    d="M11.9 7.0948C10.6998 1.47892 1.40879 5.90389 5.76035 11.6018C10.1119 17.2996 12.4 19.4908 12.4 19.4908"
                    stroke="white" />
                  <path
                    d="M11.8941 7.0948C13.0943 1.47892 22.7304 5.90389 18.3788 11.6018C14.0273 17.2996 11.7 19.5 11.7 19.5"
                    stroke="white" />
                  <path d="M11.391 6.70752L12.4043 6.70757L12.3834 7.24079H11.391V6.70752Z" fill="white" />
                </svg>
                <p>200</p>
              </div>

            </div>
          </div>
          <div class="photos-block-items photos-block-item-3" v-on:mouseenter="photosBlockItem3 = true"
            v-on:mouseleave="photosBlockItem3 = false">
            <div class="photos-block-item" v-show="photosBlockItem3">
              <div class="photos-block-item-full-screen">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <rect x="4.5" y="6.5" width="13" height="13" rx="1.5" stroke="white" />
                  <path
                    d="M6.33784 6.63126L6.33784 6.49958C6.33784 5.39501 7.23327 4.49958 8.33784 4.49958L17.5 4.49959C18.6045 4.49959 19.5 5.39502 19.5 6.49959L19.5 15.9382C19.5 16.9853 18.5159 17.7537 17.5 17.4997V17.4997"
                    stroke="white" />
                </svg>
              </div>
              <div class="photos-block-item-product">
                <svg width="48" height="48" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M11.2445 14.2998H36.7555C38.2133 14.2998 39.3618 15.542 39.2478 16.9953L37.5851 38.1953C37.4831 39.4962 36.3976 40.4998 35.0927 40.4998H12.9073C11.6024 40.4998 10.5169 39.4962 10.4149 38.1953L8.75216 16.9953C8.63818 15.542 9.78674 14.2998 11.2445 14.2998Z"
                    stroke="white" />
                  <path d="M15.004 24.4857C15.004 24.4857 14.5437 7 23.5 7C32.4563 7 31.996 24.4857 31.996 24.4857"
                    stroke="white" />
                </svg>
              </div>
              <p class="photos-block-item-paragraph">Узнай, что на мне</p>
              <div class="photos-block-item-likes">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M12.4287 7.25725L13.7612 5.03654L17.1965 5.46595L18.5 7.63849V10.3206L12.0145 18.1959L5.93878 10.2507L5.05633 8.04458L6.34555 5.89588L9.35443 4.60636L11.6159 7.32009L12.0665 7.86089L12.4287 7.25725Z"
                    fill="white" stroke="white" />
                  <path
                    d="M11.9 7.0948C10.6998 1.47892 1.40879 5.90389 5.76035 11.6018C10.1119 17.2996 12.4 19.4908 12.4 19.4908"
                    stroke="white" />
                  <path
                    d="M11.8941 7.0948C13.0943 1.47892 22.7304 5.90389 18.3788 11.6018C14.0273 17.2996 11.7 19.5 11.7 19.5"
                    stroke="white" />
                  <path d="M11.391 6.70752L12.4043 6.70757L12.3834 7.24079H11.391V6.70752Z" fill="white" />
                </svg>
                <p>200</p>
              </div>

            </div>
          </div>


        </div>
        <div class="photos-block-line">
          <div class="photos-block-items photos-block-item-4" v-on:mouseenter="photosBlockItem4 = true"
            v-on:mouseleave="photosBlockItem4 = false">
            <div class="photos-block-item" v-show="photosBlockItem4">
              <div class="photos-block-item-full-screen">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <rect x="4.5" y="6.5" width="13" height="13" rx="1.5" stroke="white" />
                  <path
                    d="M6.33784 6.63126L6.33784 6.49958C6.33784 5.39501 7.23327 4.49958 8.33784 4.49958L17.5 4.49959C18.6045 4.49959 19.5 5.39502 19.5 6.49959L19.5 15.9382C19.5 16.9853 18.5159 17.7537 17.5 17.4997V17.4997"
                    stroke="white" />
                </svg>
              </div>
              <div class="photos-block-item-product">
                <svg width="48" height="48" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M11.2445 14.2998H36.7555C38.2133 14.2998 39.3618 15.542 39.2478 16.9953L37.5851 38.1953C37.4831 39.4962 36.3976 40.4998 35.0927 40.4998H12.9073C11.6024 40.4998 10.5169 39.4962 10.4149 38.1953L8.75216 16.9953C8.63818 15.542 9.78674 14.2998 11.2445 14.2998Z"
                    stroke="white" />
                  <path d="M15.004 24.4857C15.004 24.4857 14.5437 7 23.5 7C32.4563 7 31.996 24.4857 31.996 24.4857"
                    stroke="white" />
                </svg>
              </div>
              <p class="photos-block-item-paragraph">Узнай, что на мне</p>
              <div class="photos-block-item-likes">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M12.4287 7.25725L13.7612 5.03654L17.1965 5.46595L18.5 7.63849V10.3206L12.0145 18.1959L5.93878 10.2507L5.05633 8.04458L6.34555 5.89588L9.35443 4.60636L11.6159 7.32009L12.0665 7.86089L12.4287 7.25725Z"
                    fill="white" stroke="white" />
                  <path
                    d="M11.9 7.0948C10.6998 1.47892 1.40879 5.90389 5.76035 11.6018C10.1119 17.2996 12.4 19.4908 12.4 19.4908"
                    stroke="white" />
                  <path
                    d="M11.8941 7.0948C13.0943 1.47892 22.7304 5.90389 18.3788 11.6018C14.0273 17.2996 11.7 19.5 11.7 19.5"
                    stroke="white" />
                  <path d="M11.391 6.70752L12.4043 6.70757L12.3834 7.24079H11.391V6.70752Z" fill="white" />
                </svg>
                <p>200</p>
              </div>

            </div>
          </div>
          <div class="photos-block-items photos-block-item-5" v-on:mouseenter="photosBlockItem5 = true"
            v-on:mouseleave="photosBlockItem5 = false">
            <div class="photos-block-item " v-show="photosBlockItem5">
              <div class="photos-block-item-full-screen">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <rect x="4.5" y="6.5" width="13" height="13" rx="1.5" stroke="white" />
                  <path
                    d="M6.33784 6.63126L6.33784 6.49958C6.33784 5.39501 7.23327 4.49958 8.33784 4.49958L17.5 4.49959C18.6045 4.49959 19.5 5.39502 19.5 6.49959L19.5 15.9382C19.5 16.9853 18.5159 17.7537 17.5 17.4997V17.4997"
                    stroke="white" />
                </svg>
              </div>
              <div class="photos-block-item-product">
                <svg width="48" height="48" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M11.2445 14.2998H36.7555C38.2133 14.2998 39.3618 15.542 39.2478 16.9953L37.5851 38.1953C37.4831 39.4962 36.3976 40.4998 35.0927 40.4998H12.9073C11.6024 40.4998 10.5169 39.4962 10.4149 38.1953L8.75216 16.9953C8.63818 15.542 9.78674 14.2998 11.2445 14.2998Z"
                    stroke="white" />
                  <path d="M15.004 24.4857C15.004 24.4857 14.5437 7 23.5 7C32.4563 7 31.996 24.4857 31.996 24.4857"
                    stroke="white" />
                </svg>
              </div>
              <p class="photos-block-item-paragraph">Узнай, что на мне</p>
              <div class="photos-block-item-likes">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M12.4287 7.25725L13.7612 5.03654L17.1965 5.46595L18.5 7.63849V10.3206L12.0145 18.1959L5.93878 10.2507L5.05633 8.04458L6.34555 5.89588L9.35443 4.60636L11.6159 7.32009L12.0665 7.86089L12.4287 7.25725Z"
                    fill="white" stroke="white" />
                  <path
                    d="M11.9 7.0948C10.6998 1.47892 1.40879 5.90389 5.76035 11.6018C10.1119 17.2996 12.4 19.4908 12.4 19.4908"
                    stroke="white" />
                  <path
                    d="M11.8941 7.0948C13.0943 1.47892 22.7304 5.90389 18.3788 11.6018C14.0273 17.2996 11.7 19.5 11.7 19.5"
                    stroke="white" />
                  <path d="M11.391 6.70752L12.4043 6.70757L12.3834 7.24079H11.391V6.70752Z" fill="white" />
                </svg>
                <p>200</p>
              </div>

            </div>
          </div>


        </div>
      </div>
    </div>
  </div>
  <TheFooter />
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import TheFooter from './components/TheFooter.vue'
import TheCarousel from './components/TheCarousel.vue'
export default {
  name: 'App',
  components: {
    TheHeader,
    TheFooter,
    TheCarousel,
  },
  data() {
    return {
      headerHidden: false,
      counter: 1,
      productName: 'Пижама для девочек',
      addToCartClicked: false,
      likeClicked: false,
      photosBlockItem1: false,
      photosBlockItem2: false,
      photosBlockItem3: false,
      photosBlockItem4: false,
      photosBlockItem5: false,
      cards: [
        {
          imgName: 'slide1.png'
        },
        {
          imgName: 'slide2.png'
        },
        {
          imgName: 'slide3.png'
        },
        {
          imgName: 'slide4.png'
        },
        {
          imgName: 'slide5.png'
        },
      ],
    }
  },
  created() {
    window.addEventListener('scroll', () => {
      let scrollTop = window.pageYOffset || document.documentElement.scrollTop;
      if (scrollTop > 100 ? false : true) {
        this.headerHidden = true;
      }
      if (scrollTop === 0) {
        this.headerHidden = false
      }
    })
  },
  methods: {
    minusCounter() {
      if (this.counter >= 2) {
        this.counter--
      }
    },
    addToCart(){
      const toggleAddToCart = () => {
        this.addToCartClicked = !this.addToCartClicked;
      };
      setTimeout(toggleAddToCart, 1000);
      setTimeout(toggleAddToCart, 2000);
      
    },
    like(){
      const toggleLikeInterval = () => {
        this.likeClicked = !this.likeClicked;
      };
      setTimeout(toggleLikeInterval, 1000);
      setTimeout(toggleLikeInterval, 2000);
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600;700&display=swap');

html,body,div,span,applet,object,iframe,h1,h2,h3,h4,h5,h6,p,blockquote,pre,a,abbr,acronym,address,big,cite,code,del,dfn,em,img,ins,kbd,q,s,samp,small,strike,strong,sub,sup,tt,var,b,u,i,center,dl,dt,dd,ol,ul,li,fieldset,form,label,legend,table,caption,tbody,tfoot,thead,tr,th,td,article,aside,canvas,details,embed,figure,figcaption,footer,header,hgroup,menu,nav,output,ruby,section,summary,time,mark,audio,video {
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 100%;
  font: inherit;
  vertical-align: baseline;
}
article,aside,details,figcaption,figure,footer,header,hgroup,menu,nav,section {display: block}
html {height: 100%}
body {line-height: 1}
ol,ul {list-style: none}
blockquote,q {quotes: none}
blockquote:before,blockquote:after,q:before,q:after {content: '';  content: none;}
table {border-collapse: collapse;  border-spacing: 0;}
body {font-family: 'Open Sans', sans-serif; overflow-x: hidden;}

.addToCart-relative{
  position: relative;
}
.addToCart-absolute{
  position: absolute;
  top: 50px;
  width: 600px;
}
.likeClicked-absolute{
  position: absolute;
  left: 0;
  top: 50px;
  width: 300px;
}

.header-position {
  position: sticky;
  top: 0;
  transition: 1s;
  z-index: 99999;

}

.headerHidden {
  transform: translateY(-100%);
}

.main {
  max-width: 1390px;
  margin: 0 auto;
}

.product-block-line {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  min-height: 936px;
  margin-top: 24px;
}


.product-slider {
  position: relative;
  width: 686px;
  margin-right: 36px;
}

.carousel {
  position: absolute;
  width: 100%;
}
.product-block{
  display: flex;
  flex-direction: column;
}
.product-block h2 {
  font-weight: 600;
  font-size: 18px;
  color: #333333;
  line-height: 24px;
  margin-bottom: 8px;
}

.product-block span {
  font-weight: 400;
  font-size: 12px;
  color: #828282;
  line-height: 16px;
  display: block;
  margin-bottom: 18px;
}


.comment-block {
  display: flex;
  flex-direction: row;
}

.comment-block p {
  margin-right: 12px;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  color: #333333;
}

.comment-block .stars {
  display: flex;
  flex-direction: row;
  align-items: center;
}

.comment-block .stars svg {
  display: block;
  margin-right: 1px;
}

.comment-block a {
  display: block;
  margin-left: 4px;
  margin-right: 8px;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.04em;
  color: #333333;
  text-decoration: none;
}

.comment-block a:hover {
  text-decoration: underline;
}

.product-block-price {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-top: 46px;
  margin-bottom: 8px;
}

.product-block-price-item {
  margin-right: 12px;
  font-weight: 700;
  font-size: 24px;
  line-height: 24px;
  letter-spacing: 0.04em;
  text-transform: uppercase;
  color: #333333;
}

.product-block-price-item-sale {
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.04em;
  text-decoration-line: line-through;
  color: #828282;
  margin-right: 20px;
}


.product-block-sales {
  display: flex;
  flex-direction: row;
  margin-bottom: 20px;
}

.product-block-sales p {
  margin-right: 9px;
  padding: 4px 8px;
  font-weight: 400;
  font-size: 12px;
  line-height: 16px;
  letter-spacing: 0.04em;
  color: #333333;
  border: 1px solid black;
}

.product-block-sizes {
  display: flex;
  flex-direction: column;
  margin-bottom: 40px;
}

.product-block-sizes select {
  display: block;
  width: 315px;
  padding: 12px 16px;
}

.product-block-sizes a {
  display: block;
  margin-top: 12px;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.04em;
  text-decoration-line: underline;
  color: #333333;
}


.product-block-amount {
  display: flex;
  flex-direction: column;
  width: 686px;
  border-bottom: 0.5px solid #C4C4C4;
  margin-bottom: 24px;
}

.product-block-amount a {
  display: block;
  margin-top: 12px;
  margin-bottom: 29px;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.04em;
  text-decoration-line: underline;
  color: #333333;
}

.product-block-amount .addToCart {
  display: flex;
}

.product-block-amount .addToCart .counter {
  display: flex;
  flex-direction: row;
  background: #F2F2F2;
  padding: 12px 20px;
  margin-right: 12px;
}

.product-block-amount .addToCart .counter p {
  margin-right: 40px;
  font-size: 14px;
  cursor: pointer;
}

.product-block-amount .addToCart .counter p:last-of-type {
  margin-right: 0;
}

.addToCart-line {
  display: flex;
  flex-direction: row;
  height: 44px;
}

.addToCart-line button {
  height: 44px;
  background: #333333;
  border: 1px solid #333333;
  margin-right: 4px;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.04em;
  color: #FFFFFF;
  cursor: pointer;
}

.addToCart-line button:hover {
  background: #686868;
}

.addToCart-line svg {
  width: 44px;
  height: 42px;
  display: block;
  background: #333333;
  border: 1px solid #333333;
  cursor: pointer;
}

.addToCart-line svg:hover {
  background: #686868;
}


.counter {
  display: flex;
  flex-direction: row;
}

.counter p {
  margin-right: 15px;
}


.product-block-about {
  display: flex;
  flex-direction: column;
}

.product-block-about a {
  width: 170px;
}

.product-block-about .product-block-about-item {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-bottom: 12px;
}

.product-block-about .product-block-about-item p {
  margin-left: 7px;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.04em;
  text-decoration-line: underline;
  color: #333333;
}

.product-block-about-item-pay {
  padding-left: 4px;
}

.product-block-about-item-pay p {
  margin-left: 0;
}



.see-all-styles {
  display: flex;
  justify-content: center;
  margin-top: 32px;
  margin-bottom: 32px;
}

.see-all-styles a {
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.04em;
  text-decoration: underline;
  color: #333333;
}


.photos-block {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  margin-bottom: 142px;
}

.photos-blocks-line {
  display: flex;
  flex-direction: column;
  margin-left: 16px;
}

.photos-block-line {
  display: flex;
  flex-direction: row;
  margin-bottom: 16px;
}

.photos-block-items {
  width: 100%;
  height: 100%;
}

.photos-block-item-big-block {
  width: 50%;
  height: 615px;
  background: center/cover no-repeat url(./img/1.png);
}

.photos-block-item-2 {
  min-width: 400px;
  min-height: 300px;
  margin-right: 16px;
  background: center/cover no-repeat url(./img/2.png);
}

.photos-block-item-3 {
  min-width: 400px;
  min-height: 300px;
  background: center/cover no-repeat url(./img/3.png);
}

.photos-block-item-4 {
  min-width: 400px;
  min-height: 300px;
  margin-right: 16px;
  background: center/cover no-repeat url(./img/4.png);
}

.photos-block-item-5 {
  min-width: 400px;
  min-height: 300px;
  background: center/cover no-repeat url(./img/5.png);
}

.photos-block-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: rgba(51, 51, 51, 0.7);
  width: 100%;
  height: 100%;
  position: relative;
}

.photos-block-item-full-screen {
  position: absolute;
  z-index: 9999;
  top: 12px;
  right: 12px;
}

.photos-block-item-likes {
  display: flex;
  flex-direction: row;
  align-items: center;
  position: absolute;
  z-index: 9999;
  bottom: 20px;
}

.photos-block-item-product {
  position: absolute;
  z-index: 9999;
  top: 40%;
}

.photos-block-item-paragraph {
  position: absolute;
  z-index: 9999;
  top: 60%
}

.photos-block-item p {
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.04em;
  color: #FFFFFF;
}

@media screen and (max-width: 1439px) {
  .product-slider {
    margin-right: 0;
    margin-bottom: 24px;
  }

  .product-block-line {
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .photos-block {
    justify-content: center;
  }

  .photos-block-item-big-block {
    width: 80%;
  }

  .photos-blocks-line {
    display: flex;
    flex-direction: column;
    margin-top: 16px;
    margin-left: 0;
  }
}
@media screen and (min-width: 1440px) {
  .product-block-line {
  flex-wrap: nowrap;
  }
  .photos-block {
  flex-wrap: nowrap;
}
}
@media screen and (max-width: 768px) {
  
  .photos-block-item-2 {
  min-width: 300px;
  min-height: 300px;
  margin-right: 16px;
  background: center/cover no-repeat url(./img/2.png);
}

.photos-block-item-3 {
  min-width: 300px;
  min-height: 300px;
  background: center/cover no-repeat url(./img/3.png);
}

.photos-block-item-4 {
  min-width: 300px;
  min-height: 300px;
  margin-right: 16px;
  background: center/cover no-repeat url(./img/4.png);
}

.photos-block-item-5 {
  min-width: 300px;
  min-height: 300px;
  background: center/cover no-repeat url(./img/5.png);
}
  .product-slider {
  width: 100%;
  margin-right: 0;
  }
  .product-block-line {
    display: block;
  }  
  .product-block{
    padding: 20px;
  }
  .addToCart{
    flex-direction: column;
  }
  .counter{
    width: 145px;
    margin-bottom: 15px;
  }
}
@media screen and (max-width: 500px) {
  .product-slider {
    width: 100%;
  }
  .photos-block-item-big-block{
    width: 100%;
  }
}

@media screen and (max-width: 425px){
  .product-block-sizes select{
    width: 100%;
  }
  .photos-block-item-2 {
  min-width: 200px;
  min-height: 200px;
  margin-right: 6px;
}

.photos-block-item-3 {
  min-width: 200px;
  min-height: 200px;
}

.photos-block-item-4 {
  min-width: 200px;
  min-height: 200px;
  margin-right: 6px;
}

.photos-block-item-5 {
  min-width: 200px;
  min-height: 200px;
}
}
@media screen and (max-width: 375px){  
  .photos-block{
    display: block;
  }
  .photos-block-item-2 {
  min-width: 150px;
  min-height: 150px;
  margin-right: 6px;
  background: center/cover no-repeat url(./img/2.png);
}

.photos-block-item-3 {
  min-width: 150px;
  min-height: 150px;
  background: center/cover no-repeat url(./img/3.png);
}

.photos-block-item-4 {
  min-width: 150px;
  min-height: 150px;
  margin-right: 6px;
  background: center/cover no-repeat url(./img/4.png);
}

.photos-block-item-5 {
  min-width: 150px;
  min-height: 150px;
  background: center/cover no-repeat url(./img/5.png);
}
}
</style>
