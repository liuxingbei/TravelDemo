<template>
    <div class="list" ref="wrapper">
        <div>
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="btn-list">
                    <div class="btn-wrapper">
                        <div class="btn">{{this.currentCity}}</div>
                    </div>                   
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="btn-list">
                    <div class="btn-wrapper" v-for="item of hotCities" :key="item.id">
                        <div class="btn" @click="changeCityAction(item.name)">{{item.name}}</div>
                    </div>        
                </div>
            </div>
            <div class="area" v-for="(outItem,outKey) of cities" :key="outKey" :ref="outKey">
                <div class="title border-topbottom" >{{outKey}}</div>
                <div class="item-list">
                    <div class="item border-bottom" v-for="innerItem of outItem" :key="innerItem.id" @click="changeCityAction(innerItem.name)">{{innerItem.name}}</div>               
                </div>
               
            </div>
        </div>
    </div>
</template>
<script>
    import Bscroll from 'better-scroll'
    import { mapState,mapMutations, mapActions} from 'vuex'
    export default {
        name: 'List',
        mounted() {
            this.scroll = new Bscroll(this.$refs.wrapper);
        },
        props:{
            cities:Object,
            hotCities:Array,
            letter:String
        },
        computed:{
            ...mapState({
                currentCity:'city'
            })
        },
        watch:{
            letter(){
                const element=this.$refs[this.letter][0];
                this.scroll.scrollToElement(element);
            }
        },
        methods:{
            
        },
        methods:{
            ...mapMutations(['changeCity']),      
            changeCityAction(city){
                this.changeCity(city)
                this.$router.push('/');
                
            },
        }
    }
</script>
<style lang="scss" scoped>
    @import '~@css/varibles.scss';
    .border-topbottom {
        &:before {
            border-color: #ccc;
        }
        &:after {
            border-color: #ccc;
        }
    }

    .border-bottom {
        &:before {
            border-color: #ccc;
        }

    }

    .list {
        overflow: hidden;
        position: absolute;
        top: 1.58rem;
        left: 0;
        right: 0;
        bottom: 0;
        .title {
            line-height: .44rem;
            background: #eee;
            padding-left: .2rem;
            font-size: .26rem;
            color: #666;

        }

        .btn-list {
            padding: .1rem;
            overflow: hidden;
            .btn-wrapper {
                float: left;
                width: 33.33%;
                box-sizing: border-box;
                .btn {
                    text-align: center;
                    margin: .2rem;
                    padding: .2rem;
                    border: .02rem solid #ccc;
                    font-size: .26rem;
                    cursor: pointer;
                }
            }
        }
        .item-list {
            .item {
                line-height: .76rem;
                padding-left: .36rem;
            }
        }
    }
</style>