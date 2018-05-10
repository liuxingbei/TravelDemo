<template>
    <div>
        <div class="recommend-title">热销推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item in RecommendList" :key="item.id">
                <img :src="item.url" alt="" class="item-img">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-btn">查看详情</button>
                </div>
            </li>
        </ul>
    </div>

</template>
<script>
    export default {
        name: 'Recommend',
        data() {
            return {
                RecommendList: [
                    {
                        id: 0,
                        url: 'http://img1.qunarzz.com/sight/p0/1803/7b/7b023b9728f0834fa3.img.jpg_200x200_5fddc1d8.jpg',
                        title: '世界花卉大观园',
                        desc: '揽天下奇花异草，聚世界经典园林揽天下奇花异草，聚世界经典园林揽天下奇花异草，聚世界经典园林揽天下奇花异草，聚世界经典园林揽天下奇花异草，聚世界经典园林'
                    },
                    {
                        id: 1,
                        url: 'http://img1.qunarzz.com/sight/p0/1508/a5/4003f9dd7bebf61eccbf64046e26d487.water.jpg_200x200_7690e4cd.jpg',
                        title: '北京欢乐谷',
                        desc: '👍小伙伴们都收藏了，去看看吧~'
                    },
                    {
                        id: 2,
                        url: 'http://img1.qunarzz.com/sight/p0/1704/d6/d62a708bc69472f5a3.img.jpg_200x200_5193a3b6.jpg',
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
        display: flex;
        height: 1.9rem;

        .item-img {
            width: 1.7rem;
            height: 1.7rem;
            padding: .1rem;
        }
        .item-info {
            flex: 1;
            padding: .1rem;
            min-width: 0;
            .item-title {
                line-height: .54rem;
                font-size: .32rem;
            }
            .item-desc {         
                @include ellipsis;
                line-height: .4rem;
                color: #bbb;
            }
            .item-btn {
                background: #ff9300;
                line-height: .44rem;
                margin-top: .16rem;
                padding: 0 .2rem;
                color: #fff;
            }
        }
    }
</style>