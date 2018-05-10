<template>
    <div class="header">
        <div class="header-left">
            <div class="iconfont icon-fanhui back-icon"></div>
        </div>
        <div class="header-input">
            <span class="iconfont icon-sousuo"></span>
            搜索旅行地/酒店/景点

        </div>
         <router-link to="/city">
            <div class="header-right">
                    {{city}}<span class="iconfont icon-jiantou arrow-icon"></span> 
            </div>
        </router-link>
        
    </div>
</template>
<script>
    export default{
        name:'Header',
        props:{
            city:{
                type:String
            }
        }
    }
</script>
<style lang="scss" scoped>
    @import '~@css/varibles.scss';
    .header{
        height:.86rem;
        line-height: .86rem;
        color:#fff;
        /* background: red; */
        background: $bgColor;
        display: flex;
        
        .header-left{
            width:.64rem; 
            float: left; 
            .back-icon{
                text-align: center;
                font-size:.4rem
            } 
        }
        .header-input{
            flex:1;
            background: #fff;            
            color:#ccc;
            height:.64rem;
            line-height: .64rem;
            margin-top:.12rem;
            margin-left:.2rem;
            padding-left:.2rem;
            border-radius: .1rem;

        }
        .header-right{
            width:1.04rem;
            padding: 0 .1rem;
            float: right;
            text-align:center;
            color:#fff;
            .arrow-icon{
                font-size: .24rem;
            }
        }
    }
</style>