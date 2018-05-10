<template>
    <div>
        <div class="recommend-title">周末去哪儿</div>
        <ul>
            <li class="item border-bottom" v-for="item in list" :key="item.id">
                <div class="item-wrapper">
                    <img :src="item.imgUrl" alt="" class="item-img">
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
        props:{
            list:Array
        }
    }

</script>
<style lang="scss" scoped>
    @import '~@css/varibles.scss';
    .recommend-title {
        line-height: .8rem;
        background: #eee;       
        text-indent: .2rem;


    }

    .item {


        .item-wrapper {
            overflow: hidden;
            width: 100%;
            height: 0;
            padding-bottom: 37.09%;

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