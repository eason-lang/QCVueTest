<template>
    <div class="swiper-container"
         ref="slider">
        <div class="swiper-wrapper">
            <router-link class="swiper-slide"
                 v-for="slide in slides" tag="div" :to="{name:'BookDetail',params:{id:slide.id}}">
                <img :src="slide.img_url"/>
            </router-link>
        </div>

        <div class="swiper-pagination"
             ref="pagination">
        </div>

    </div>
</template>


<script type="text/ecmascript-6">

    import Swiper from "swiper"
    import 'swiper/dist/css/swiper.css'

    export default{
        props: ['slides'],

        mounted() {
            debugger
            new Swiper(this.$refs.slider, {
                pagination: this.$refs.pagination,
                paginationClickable: true,
                spaceBetween: 30,
                centeredSlides: true,
                autoplay: 2500,
                autoplayDisableOnInteraction: false
            })
        }
    }
</script>

<style>
    .swiper-container{
        width:100%;
        margin:0;
        padding:0;

    }
    .swiper-wrapper {
        height: 200px;

    }
    .swiper-slide img {
        max-width: 100%;

    }
    .swiper-slide {
        text-align: center;
        background: #fff;


        /* 垂直居中幻灯片的样式设置 */
        display: -webkit-box;
        display: -ms-flexbox;
        display: -webkit-flex;
        display: flex;
        -webkit-box-pack: center;
        -ms-flex-pack: center;
        -webkit-justify-content: center;
        justify-content: center;
        -webkit-box-align: center;
        -ms-flex-align: center;
        -webkit-align-items: center;
        align-items: center;
    }


</style>