<template>
    <div class="swiper-container">
        <div class="swiper-wrapper">
            <slot></slot>
        </div>
        <!-- Add Pagination -->
        <div class="swiper-pagination"></div>
    </div>
</template>

<script>
    import Swiper from 'swiper'
    import '../../../node_modules/swiper/swiper-bundle.css'
    export default {
        name: "swiper",
        mounted() {
            new Swiper('.swiper-container', {
                pagination: {
                    el: '.swiper-pagination',
                    dynamicBullets: true,
                },
            });
        }
    }
</script>

<style scoped>
    .swiper-container {
        width: 100%;
        border: 1px solid #fe0000;
        height: 3.70rem;
    }

    .swiper-slide {
        text-align: center;
        font-size: 18px;
        background: #fff;

        /* Center slide text vertically */
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