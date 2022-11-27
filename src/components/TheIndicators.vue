<template>
    <div>
        <ul>
            <li
                v-for="(image, index) in elements"      
                :key="index"
            >
                <img
                    :src="require(`@/img/${image.imgName}`)"    
                    :class="{'active': currentElementIndex === index}"                
                    @click="showEl(index)"
                    :hover="toggleActive"
                    class="indicatorImage"
                >
            </li>
        </ul>
    </div>
</template>
<script>
export default{
    name: 'TheIndicators',
    props: {elements: Array, currentElementIndex: Number, showEl: Function },
}
</script>
<style scoped>
li{
    display: flex;
    flex-direction: column;
    margin-bottom: 7px;
}
.indicatorImage{
    display: block;
    width: 70px;
    height: 91px;
    opacity: 0.5;
}
@media screen and (max-width: 425px) {
.indicatorImage{
    width: 40px;
    height: 52px;
}
}
.active {
    opacity: 1;
}
</style>