<template>
    <div class="testimonials testimonials--slider">
        <swiper
            ref="mySwiperRef"
            class="horizontal-swiper"
            :options="swiperOptions"
            
        >
            <swiper-slide 
                v-for="item in items" 
                :key="item.id"
            >
                <article class="testimonials--slider__item">
                    <div class="testimonials--slider__inner">
                        <div
                            v-if="item.image"
                            class="testimonials--slider__image"
                        >
                            <img :src="require(`../../assets/images/${item.image}`)">
                        </div>
                        <div
                            v-else
                            class="testimonials--slider__image"
                        >
                            <img :src="require('../../assets/images/man.png')">
                        </div>
                        <div class="testimonials__customer-info">
                            <h4
                                v-if="item.name"
                                class="ta-c testimonials__customer-info__name"
                            >
                                {{ item.name }}
                            </h4>
                        </div>
                        <p
                            v-if="item.text"
                            class="text"
                            v-html="item.text"
                        />
                    </div>
                </article>
            </swiper-slide>
        </swiper>
    </div>
</template>

<script>
import 'swiper/css/swiper.css';
import { Swiper, SwiperSlide } from 'vue-awesome-swiper';
export default {
    name:'cTesimonial',

    data() {
        return {
            swiperOptions: {
                loop: true,
                autoplay:true,
                spaceBetween: 0,
                slideToClickedSlide: true,
                slidesPerView:1,
                navigation: {
                    nextEl: '.swiper-button-next',
                    prevEl: '.swiper-button-prev'
                },
            }
        }
    },

    components: {
        Swiper,
        SwiperSlide
    },

    props:{
        /**
         * Items
         */
        items:Array,
    },
}
</script>

<style lang="scss" src="../../assets/scss/Style.scss" />
