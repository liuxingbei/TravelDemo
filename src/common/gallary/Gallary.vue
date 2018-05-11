<template>
    <div class="container" @click="handleGallaryClick">
        <div class="wrapper">
                <swiper :options="swiperOptions">
                        <!-- slides -->
                        <swiper-slide v-for="(item,index) of imgs" :key="index">
                            <img class="gallary-img" :src="item" alt="">
                        </swiper-slide>
                    
                        <!-- Optional controls -->
                        <div class="swiper-pagination" slot="pagination"></div>
            
            
                    </swiper>
        </div>
    </div>
</template>
<script>
    import {swiper,swiperSlide} from 'vue-awesome-swiper'
    export default{
        name:'CommonGallary',
        data(){
            return {
                swiperOptions:{
                    pagination:'.swiper-pagination',
                    paginationType : 'fraction',
                    observeParents:true,
                    observer:true
                }
            }
        },
        props:{
            imgs:{
                type:Array,
                default(){
                    return []
                }
            }
        },
        methods:{
            handleGallaryClick(){
                this.$emit('close')
            }
        }
    }
</script>
<style lang="scss" scoped>
    
    .container{
        display: flex;
        flex-direction: column;
        justify-content: center;
        z-index: 99;
        position: fixed;
        left:0;
        right: 0;
        top: 0;
        bottom: 0;
        background: #000;
        .wrapper{
            height:0;
            padding-bottom:100%;
            .gallary-img{
                width:100%;
            }

            .swiper-pagination{
                color:#fff;
                bottom:-1rem;
            }

        }
    }
</style>
<style>
.container .swiper-container{
        overflow: inherit;
    }
</style>