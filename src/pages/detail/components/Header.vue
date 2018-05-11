<template>
    <div>
        <router-link class="header-abs" tag="div" to="/" v-show="showAbs">
            <span class="iconfont icon-fanhui abs-back"></span>
        </router-link>
        <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
                <router-link to="/">
                    <div class="iconfont icon-fanhui header-back"></div>
                </router-link>
            城市选择
        </div>
    </div>
</template>
<script>
    export default{
        name:'DetailHeader',
        data(){
            return{
                showAbs:true,
                opacityStyle:{
                    opacity:0
                }
            }
        },
        activated(){
            window.addEventListener('scroll',this.handleScroll)
        },
        deactivated(){
            window.removeEventListener('scroll',this.handleScroll)
        },
        methods:{
            handleScroll(){
                console.log("scroll");
                const top=document.documentElement.scrollTop
               
                if(top>60 ){
                    const opacity=top/140;
                    opacity>1?1:opacity;
                    this.opacityStyle={
                        opacity
                    }
                    this.showAbs=false;
                }else{
                    this.showAbs=true;
                }
            }
        }
    }
</script>
<style lang="scss" scoped>
    @import '@css/varibles.scss';
    .header-abs{
        position: absolute;
        top:.2rem;
        left:.2rem;
        width: .8rem;
        height: .8rem;
        line-height: .8rem;
        text-align:center;
        background: rgba(0,0,0,.8);
        border-radius: 50%;
        .abs-back{
            color:#fff;
            font-size:.3rem;
        }


    }
    .header-fixed{
        position: fixed;
        top:0;
        left:0;
        right: 0;
        background: $bgColor;
        height: .86rem;
        line-height:.86rem;
        text-align:center;
        font-size:.32rem;
        color:#fff;
        z-index:99;
        .header-back{
            width: .64rem;
            text-align: center;
            font-size: .4rem;
            position: absolute;
            top:0;
            left:0;
            color:#fff;
            
        }
    }


</style>