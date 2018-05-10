<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <!-- slides -->
            <swiper-slide v-for="item of swiperList" :key="item.id">
                <img :src="item.url" alt="">
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
                    loop:true,
                    autoplay:3000

                },
                swiperList:[
                    {
                        id:0,
                        url:'http://img1.qunarzz.com/piao/fusion/1805/77/f63bd04dd5319602.jpg_750x200_6ba8e0ca.jpg'
                    },
                    {
                        id:1,
                        url:'http://img1.qunarzz.com/piao/fusion/1804/bd/8e4a1c3f470d3702.jpg_750x200_f1f0a8c7.jpg'
                    },
                    {
                        id:2,
                        url:'http://img1.qunarzz.com/piao/fusion/1801/bd/04554e7c67650302.jpg_750x200_4293d60a.jpg'
                    }
                ]
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
    .swiper-pagination-bullet-active{
        background:#fff;
    }
</style>