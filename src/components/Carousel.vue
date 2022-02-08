<template>
    <div class="img-container" >   
        <div style="position: relative;width: 100%;height: 100%;">   
        <vueper-slides
        class="no-shadow"
        :arrows="false"
        :visible-slides="4"
        slide-multiple
        :gap="1"
        :slide-ratio="1 / 7"
        :dragging-distance="200"
        :breakpoints="{ 800: { visibleSlides: 3, slideMultiple: 3, slideRatio: 1/4 } }"
        >
        <vueper-slide v-for="(slide, i) in state.slides" :key="i" :image="slide.image" />
        </vueper-slides>
    </div>
    </div>
</template>

<script >
import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'
import 'vueperslides/dist/styles.css'
import {reactive} from 'vue'

export default{
    components: {VueperSlides, VueperSlide},
    setup(){
         const state = reactive({ 
             slides: [
                {
                    image: require('@/assets/slide1.png')
                },
                {
                    image: require('@/assets/slide2.png')
                },
                {
                    image: require('@/assets/slide1.png')
                },
                {
                    image: require('@/assets/slide2.png')
                },
                {
                    image: require('@/assets/slide1.png')
                },
                {
                    image: require('@/assets/slide2.png')
                },
                {
                    image: require('@/assets/slide1.png')
                },
                {
                    image: require('@/assets/slide2.png')
                },
                {
                    image: require('@/assets/slide1.png')
                },
                {
                    image: require('@/assets/slide2.png')
                },
                {
                    image: require('@/assets/slide1.png')
                },
                {
                    image: require('@/assets/slide2.png')
                }
                // Other slides.
        ]});
  return {state}
            },
}
         
</script>

<style lang="scss" scoped>
        .img-container {
            max-width: 900px;
            width: 100%;
            height: 100%;
            position: relative;
            margin: auto;
            display: flex;
            // padding-right: 55px;
                        img{
                            width: 200px;
            height: 100%;
            padding: 5px;
            position: absolute;
            left: 0;
            right: 0;
            bottom: 0;
            top: 0;
                }
        }

</style>