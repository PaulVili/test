<template>
    <div>
        <img
          :src="require(`@/img/${imgName}`)"
        >
    </div>
</template>
<script>
export default {
  name: 'TheCard',
  props: {imgName: String}
}
</script>
<style scoped>
img{
  display: block;
  width: 100%;
  height: 100%;
}
</style>