<template>
    <div>
        <div class="search">
            <input v-model="keyword" type="text" class="search-input" placeholder="输入城市名或拼音">
        </div>
        <div class="search-content" ref="search" v-show="keyword">
            <ul>
                <li v-for="item of list" class="border-bottom item" :key="item.id" @click="changeCityAction(item.name)">{{item.name}}</li>
                <li v-show="hasNoData" class="border-bottom item">没有找到匹配数据</li>
            </ul>
        </div>
    </div>

</template>
<script>
    import Bscroll from 'better-scroll'
    import {mapMutations} from 'vuex'
    export default {
        name: 'Search',
        props: {
            cities: Object
        },
        data() {
            return {
                keyword: '',
                list: [],
                timer: null
            }
        },
        mounted(){
            this.scroll=new Bscroll(this.$refs.search);
        },
        computed:{
            hasNoData(){
                return !this.list.length;
            }
        },
        watch: {
            keyword() {
                if (this.timer) {
                    clearTimeout(this.timer);
                    
                }
                if(!this.keyword){
                    this.list=[];
                    return;
                }
                this.timer = setTimeout(() => {
                    const result=[];
                    for (let i in this.cities) {
                        this.cities[i].forEach(value => {
                            if (value.name.indexOf(this.keyword) > -1 || value.spell.indexOf(this.keyword) > -1) {
                                result.push(value);
                            }
                        });
                    }
                    this.list=result;
                }, 100)


            }
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
    .search {

        height: .72rem;
        line-height: .72rem;
        background: $bgColor;
        padding: 0 .1rem;
        box-sizing: border-box;
        .search-input {
            width: 100%;
            box-sizing: border-box;
            height: .62rem;
            line-height: .62rem;
            text-align: center;
            padding: 0 .1rem;
            border-radius: .06rem;
            color: #666;
        }
    }

    .search-content {
        overflow: hidden;
        position: absolute;
        top: 1.58rem;
        left: 0;
        right: 0;
        bottom: 0;
        background: #eee;
        z-index: 1;
        .item{
            line-height: .62rem;
            text-indent:.2rem;
            background:#fff;
        }
    }
</style>