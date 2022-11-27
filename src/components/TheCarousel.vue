<template>
    <div class="relative">
        <TheCard :imgName="currentEl.imgName" class="card"/>       
        <TheIndicators 
            class="absolute"
            :imgName="this.cards.imgName"
            :elements="this.cards"
            :currentElementIndex="this.currentElementIndex"
            :showEl="this.showEl"
            />
    </div>
</template>
<script>
import TheCard from './TheCard.vue'
import TheIndicators from './TheIndicators.vue'
export default {    
  name: 'TheCarousel',
  props:{cards: Array},
  data(){
    return {currentElementIndex: 0}
  },
  components: {
    TheCard,
    TheIndicators,
  },
  computed:{
    currentEl(){
        return this.cards[this.currentElementIndex];
    },
  },
  methods: {
      showNextEl() {
          this.currentElementIndex++;
      },
      showPrevEl() {
          this.currentElementIndex--;
      },
      showEl(elementIndex) {
          this.currentElementIndex = elementIndex;
      }
  }
}
</script>
<style scoped>
.relative{
    position: relative;
}
.absolute{
    position: absolute;
    top: 26px;
    left: 24px;
}
</style>