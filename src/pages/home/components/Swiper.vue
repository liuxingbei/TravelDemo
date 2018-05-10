<template>
    <div class="wrapper">
        <swiper :options="swiperOption" v-if="showSwiper">
            <!-- slides -->
            <swiper-slide v-for="item of list" :key="item.id">
                <img :src="item.imgUrl" alt="">
            </swiper-slide>

            <!-- Optional controls -->
            <div class="swiper-pagination" slot="pagination"></div>


        </swiper>
    </div>

</template>
<script>
    import { swiper, swiperSlide } from 'vue-awesome-swiper'
    export default {
        name: 'HomeSwiper',
        data() {
            return {
                swiperOption: {
                    pagination: '.swiper-pagination',
                    loop: true,
                    autoplay: 3000

                }
            }
        },
        props: {
            list: Array
        },
        computed: {
            showSwiper() {
                return this.list.length;
            }

        }
    }
</script>

<style lang="scss" scoped>
    .wrapper {
        width: 100%;
        height: 26.67vm;
        overflow: hidden;
        background: #eee;

        img {
            width: 100%;
        }
    }
</style>
<style>
    .swiper-pagination-bullet-active {
        background: #fff;
    }
</style>