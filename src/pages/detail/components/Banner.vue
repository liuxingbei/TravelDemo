<template>
    <div>
        <div class="banner" @click="handleBannerClick">
            <img class="banner-img" :src="banner" alt="">
            <div class="banner-info">
                <div class="banner-title">{{this.name}}</div>
                <div class="banner-number">
                    <span class="iconfont icon-image banner-icon"></span>
                    {{gallary.length}}</div>
            </div>
        </div>
        <!-- <fade-animation>
            <common-gallary :imgs="gallary" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
        </fade-animation> -->
        <common-gallary :imgs="gallary" v-show="showGallary" @close="handleGallaryClose"></common-gallary>

    </div>
</template>
<script>
    import CommonGallary from '@common/gallary/Gallary'
    import FadeAnimation from '@common/fade/FadeAnimation'
    export default {
        name: 'Banner',
        props: {
            name: String,
            banner: String,
            gallary: Array
        },
        data() {
            return {
                showGallary: false
            }
        },
        components: {
            CommonGallary,
            FadeAnimation
        },
        methods: {
            handleBannerClick() {
                this.showGallary = true;
            },
            handleGallaryClose() {
                this.showGallary = false;
            }
        }
    }
</script>
<style lang="scss" scoped>
    .banner {
        width: 100%;
        height: 0;
        overflow: hidden;
        padding-bottom: 55%;
        position: relative;
        color: #fff;

        .banner-img {
            width: 100%;
        }
        .banner-info {
            display: flex;
            position: absolute;
            left: 0;
            right: 0;
            bottom: 0;
            line-height: .6rem;
            background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8));

            .banner-title {
                flex: 1;
                padding-left: .2rem;

            }
            .banner-number {
                margin-top: .14rem;
                padding: 0 .4rem;
                height: .32rem;
                line-height: .32rem;
                border-radius: .2rem;
                background: rgba(0, 0, 0, .6);
                font-size: .24rem;
                .banner-icon {
                    font-size: .24rem;
                }

            }

        }
    }
</style>