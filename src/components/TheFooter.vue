<template>
  <div class="footer">
    <div class="footer-blocks-line">
      <div class="footer-blocks">
        <div class="footer-block">
          <h3 class="footer-heading">покупателям</h3>
          <ul>
            <li><a href="#">Каталог</a></li>
            <li><a href="#">Акции</a></li>
            <li><a href="#">Бренды</a></li>
          </ul>
        </div>
        <div class="footer-block">
          <h3 class="footer-heading">о нас</h3>
          <ul>
            <li><a href="#">О компании</a></li>
            <li><a href="#">Новости</a></li>
            <li><a href="#">Команда</a></li>
          </ul>
        </div>
      </div>
      <form>
        <h3 class="footer-heading">Узнайте первыми о новинках и акциях</h3>
        <div class="emailBlock">
          <input type="email" placeholder="Адрес электронной почты" v-model="email">
          <span class="emailCloseItem" @click="clearEmailValue">
            <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M3.70001 12.0664L12.0501 3.88337" stroke="#C4C4C4" />
              <path d="M12.2516 12.0664L3.90161 3.88335" stroke="#C4C4C4" />
            </svg>
          </span>
        </div>
        <button type="submit">Подписаться</button>
      </form>
    </div>
  </div>
</template>
  
<script>

export default {
  name: 'TheFooter',
  data(){
    return{
      email: '',
    }
  },
  methods:{
    clearEmailValue(){
      this.email = ''
    }
  }
}
</script>
  
<style scoped>
.footer{
  max-width: 1390px;
  margin: 0 auto;
}
.footer-blocks-line{
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  flex-wrap: wrap;
  padding-bottom: 70px;
}
.footer-blocks{
  display: flex;
  flex-direction: row;
  margin-bottom: 58px;
}
.footer-block{
  margin-right: 255px;
}
.footer-heading {
  text-transform: uppercase;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  letter-spacing: 0.04em;
  color: #333333;
  margin-bottom: 16px;
  max-width: 370px;
}
ul > li{
  margin-bottom: 8px;
}
ul > li> a{
  color: #333333;
  text-decoration: none;
}
ul > li> a:hover{
  color: #000;
  text-decoration: underline;
}
.emailBlock{
  width: 452px;
  padding: 12px;
  display: flex;
  flex-direction: row;
  border-bottom: 1px solid #C4C4C4;
  margin-bottom: 35px;
}
input {
  border: none;
  outline:none;
  width: 80%;
  background: none;
}
.emailCloseItem{
  display: block;
  margin-left: auto;
  margin-right: 0;
  cursor: pointer;
}
input ::placeholder {
  color: #828282;
}

button{
  background: none;
  cursor: pointer;
  padding: 8px 28px;
  border: 1px solid #333333;
  text-align: right;
  display: block;
  margin-left: auto;
  margin-right: 0;
}
button:hover{
  background: #eeeeee;
  transform: translateY(1px);
}

@media screen and (max-width: 768px) {
  .footer-block{
  margin-right: 46px;
  }
  .emailBlock{
    max-width: 335px;
  } 
}
@media screen and (max-width: 425px) {  
  .footer-heading {
  text-transform: uppercase;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  letter-spacing: 0.04em;
  color: #333333;
  margin-bottom: 16px;
  max-width: 225px;
}
  .emailBlock{
    max-width: 250px;
  } 
}
</style>
  