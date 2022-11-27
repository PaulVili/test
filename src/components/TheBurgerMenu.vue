<template >
  <div class="main" v-show="BurgerMenu">
    <div>
      <div @click="closeMenu">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="closeMenuItem">
          <g clip-path="url(#clip0_110_994)">
            <line x1="5.01046" y1="18.2822" x2="18.6464" y2="4.6462" stroke="#333333" />
            <line y1="-0.5" x2="19.2842" y2="-0.5" transform="matrix(-0.707107 -0.707107 -0.707107 0.707107 19 18.6357)"
              stroke="#333333" />
          </g>
          <defs>
            <clipPath id="clip0_110_994">
              <rect width="24" height="24" fill="white" />
            </clipPath>
          </defs>
        </svg>
      </div>
      <div class="menu-block">
        <a href="#" @click="closeMenu">постельное белье</a>
        <a href="#" @click="closeMenu">одежда для дома</a>
        <a href="#" @click="closeMenu">Одежда для улицы</a>
        <a href="#" @click="closeMenu">Выход</a>
      </div>
    </div>

  </div>
</template>
  
<script>
export default {
  name: 'TheBurgerMenu',
  data(){
    return{
      BurgerMenu: true,
    }
  },
  methods: {
    closeMenu(){
      this.BurgerMenu = !this.BurgerMenu
    }
  }
}
</script>
  
<style scoped>
.main{
  position: absolute;
  top: 0;
  left: auto;
  right: 0;
  width: 100%;
  height: 277px;
  background: #fff;
}
.menu-block{
  display: flex;
  flex-direction: column;
  margin: 30px 80px 43px;
  margin-top: 80px;
  margin-left: 30px;
  margin-bottom: 43px;
}
.closeMenuItem{
  display: block;
  position: absolute;
  cursor: pointer;
  left: auto;
  top: 18px;
  right: 20px;
}
a{
  display: block;
  color: #333333;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  font-size: 12px;
  line-height: 16px;
  font-weight: 400;
  text-decoration: none;
  margin-bottom: 30px;
}
</style>
  