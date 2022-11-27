<template>
  <div class="TheHeader">
    <div class="header">
      <h2 class="header-logo">LOGO</h2>
      <div class="header-items">
        <a href="#" class="header-item">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <circle cx="12.4595" cy="8.18919" r="3.68919" stroke="#333333" />
            <path d="M4.5 19.3379H19.5" stroke="#333333" />
            <path d="M4.5 19.84C4.5 16.4347 8.84699 13.9134 12.2143 14.0023C15.4328 14.0872 19.5 16.4347 19.5 19.84"
              stroke="#333333" />
          </svg>
        </a>
        <a href="#" class="header-item">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M11.8999 7.0948C10.6997 1.47892 1.40869 5.90389 5.76025 11.6018C10.1118 17.2996 12.3999 19.4908 12.3999 19.4908"
              stroke="#333333" />
            <path
              d="M11.8941 7.0948C13.0943 1.47892 22.7304 5.90389 18.3788 11.6018C14.0272 17.2996 11.7 19.5 11.7 19.5"
              stroke="#333333" />
            <path d="M11.391 6.70752L12.4043 6.70757L12.3834 7.24079H11.391V6.70752Z" fill="#333333" />
          </svg>
        </a>
        <a href="#" class="header-item">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M5.25468 10.5659C5.13958 9.11201 6.2884 7.86865 7.74689 7.86865H16.2531C17.7116 7.86865 18.8604 9.11201 18.7453 10.566L18.2203 17.1975C18.1174 18.4977 17.0323 19.5002 15.7281 19.5002H8.27189C6.96769 19.5002 5.88261 18.4977 5.77968 17.1975L5.25468 10.5659Z"
              stroke="#333333" />
            <path d="M8.00005 12.5C8.00005 12.5 7.78335 4 12.0001 4C16.2168 4 16.0001 12.5 16.0001 12.5"
              stroke="#333333" />
          </svg>
          <p v-if="counter > 0">{{counter}}</p>
        </a>
        <div @click="BurgerMenu=!BurgerMenu">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="burgerMenuBtn" >
          <g clip-path="url(#clip0_110_929)">
            <line x1="3" y1="5.5" x2="21" y2="5.5" stroke="#333333" />
            <line x1="3" y1="17.5" x2="21" y2="17.5" stroke="#333333" />
            <line x1="3" y1="11.5" x2="21" y2="11.5" stroke="#333333" />
          </g>
          <defs>
            <clipPath id="clip0_110_929">
              <rect width="24" height="24" fill="white" />
            </clipPath>
          </defs>
        </svg>
        </div>
      </div>
    </div>
    <TheBurgerMenu v-show="BurgerMenu" class="burger-z"/>
  </div>
</template>

<script>
import TheBurgerMenu from './TheBurgerMenu.vue'
export default {  
  name: 'TheHeader', 
  data(){
    return{
      BurgerMenu: false,
      counter: 0,
    }    
  },
  created() {
      window.addEventListener('click', (e) => {
        if (!this.$el.contains(e.target)){
          this.BurgerMenu  = false
        }
      })
  },
  components: {
    TheBurgerMenu
  },  
}
</script>

<style scoped>
.TheHeader{
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
}
.burger-z{
  z-index: 9999;
}
.header{  
  max-width: 1390px;
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.header-logo{
  margin-top: 8px;
  margin-bottom: 8px;
  font-size: 22px;
  line-height: 16px;
  font-weight: 700;
  color: #000;
  letter-spacing: 0.04em;
}

.header-items{
  margin-top: 8px;
  margin-bottom: 8px;
  display: flex;
  flex-direction: row;
}
.header-item{
  margin-right: 24px;
}
.burgerMenuBtn{
  display: none;
}

@media screen and (max-width: 1024px){
  .header{
    padding: 22px;
  }
}
@media screen and (max-width: 768px){
  .burgerMenuBtn{
    display: block;
  }
}
</style>