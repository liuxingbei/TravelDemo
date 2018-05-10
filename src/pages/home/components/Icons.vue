<template>
    <div class="icons">
        <swiper :options="swiperOption" class="swiper-container">
            <!-- slides -->
            <swiper-slide v-for="(page,index) of pages" :key="index">
                <ul class="container">
                    <li class="items" v-for="item in page" :key="item.id">
                        <router-link :to="{path:item.href}">
                            <img :src="item.url" alt="">
                            <p>{{item.title}}</p>
                        </router-link>
                    </li>
                </ul>
            </swiper-slide>

            <!-- Optional controls -->
            <div class="swiper-pagination" slot="pagination"></div>


        </swiper>
    </div>


</template>
<script>
    import {swiper,swiperSlide} from 'vue-awesome-swiper'
    export default {
        name: 'icons',
        data() {
            return {
                swiperOption:{
                    pagination:'.swiper-pagination'
                },
                iconList: [
                    {
                        id: 0,
                        url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                        title: '景点门票',
                        href: '/'
                    },
                    {
                        id: 1,
                        url: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
                        title: '必游榜单',
                        href: '/'
                    },

                    {
                        id: 2,
                        url: 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png',
                        title: '踏青赏花',
                        href: '/'
                    },
                    {
                        id: 3,
                        url: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
                        title: '一日游',
                        href: '/'
                    },
                    {
                        id: 4,
                        url: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
                        title: '动植物园',
                        href: '/'
                    },
                    {
                        id: 5,
                        url: 'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png',
                        title: '故宫',
                        href: '/'
                    },
                    {
                        id: 6,
                        url: 'http://img1.qunarzz.com/piao/fusion/1803/67/9a1678221b8e0e02.png',
                        title: '古北水镇',
                        href: '/'
                    },
                    {
                        id: 7,
                        url: 'http://img1.qunarzz.com/piao/fusion/1804/ed/cf572be30fc32f02.png',
                        title: 'Q+精选',
                        href: '/'
                    },
                    {
                        id: 8,
                        url: 'http://img1.qunarzz.com/piao/fusion/1803/67/9a1678221b8e0e02.png',
                        title: '古北水镇',
                        href: '/'
                    },
                    {
                        id: 9,
                        url: 'http://img1.qunarzz.com/piao/fusion/1804/ed/cf572be30fc32f02.png',
                        title: 'Q+精选',
                        href: '/'
                    }
                ]
            }

        },
        computed: {
            pages() {
                let pages = [];
                this.iconList.forEach((item, index) => {
                    let page = Math.floor(index / 8);
                    if (!pages[page]) {
                        pages[page] = []
                    }
                    pages[page].push(item)

                });
                return pages;

            }
        }
    }
</script>
<style lang="scss" scoped>
    @import '~@css/varibles.scss';
    .container {
        display: flex;
        justify-content: space-around;
        align-items: center;
        flex-wrap: wrap;
        padding-top: .1rem;
        box-sizing: border-box;
       

        .items {
            width: 25%;
            text-align: center;
            float: left;
            img {
                width: 1.1rem;
                height: 1.1rem;
            }
            p {
                color: #aaa;
                margin-bottom: .1rem;
            }
        }

    }
</style>