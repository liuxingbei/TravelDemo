<template>        
    <div class="header">
        <router-link to="/">
            <div class="iconfont icon-fanhui header-back"></div>
        </router-link>
        
        城市选择
    </div>
</template>
<script>
    export default {
        name: 'Header'
    }
</script>
<style lang="scss" scoped>
    @import '~@css/varibles.scss';
    .header{
        overflow: hidden;
        background: $bgColor;
        height: .86rem;
        line-height:.86rem;
        text-align:center;
        font-size:.32rem;
        color:#fff;
        position: relative;

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