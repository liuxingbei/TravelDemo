<template>
    <div>
        <div class="recommend-title">周末去哪儿</div>
        <ul>
            <li class="item border-bottom" v-for="item in RecommendList" :key="item.id">
                <div class="item-wrapper">
                    <img :src="item.url" alt="" class="item-img">
                </div>

                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>

</template>
<script>
    export default {
        name: 'Weekend',
        data() {
            return {
                RecommendList: [
                    {
                        id: 0,
                        url: 'http://img1.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
                        title: '世界花卉大观园',
                        desc: '揽天下奇花异草，聚世界经典园林揽天下奇花异草，聚世界经典园林揽天下奇花异草，聚世界经典园林揽天下奇花异草，聚世界经典园林揽天下奇花异草，聚世界经典园林'
                    },
                    {
                        id: 1,
                        url: 'http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg',
                        title: '北京欢乐谷',
                        desc: '👍小伙伴们都收藏了，去看看吧~'
                    },
                    {
                        id: 2,
                        url: 'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg',
                        title: '十渡聚龙湾玻璃栈道',
                        desc: ''
                    }


                ]
            }
        }
    }

</script>
<style lang="scss" scoped>
    @import '~@css/varibles.scss';
    .recommend-title {
        line-height: .8rem;
        background: #eee;
        margin-top: .2rem;
        text-indent: .2rem;


    }

    .item {


        .item-wrapper {
            overflow: hidden;
            width: 100%;
            height: 0;
            padding-bottom: 33.43%;

            .item-img {
                width: 100%;

            }
        }


        .item-info {
            padding: .1rem;
            min-width: 0;
            .item-title {
                text-indent: .2rem;
                line-height: .54rem;
                font-size: .32rem;
            }
            .item-desc {
                @include ellipsis;
                line-height: .4rem;
                color: #bbb;
            }

        }
    }
</style>