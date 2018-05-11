<template>
    <div>
        <detail-banner :name="sightName" :banner="bannerImg" :gallary="gallaryImgs"></detail-banner>
        <detail-header></detail-header>
        <detail-list :list="categoryList"></detail-list> 
               
    </div>
</template>
<script>
    import DetailBanner from './components/Banner.vue'
    import DetailHeader from './components/Header.vue'
    import DetailList from './components/List.vue'
    import axios from 'axios'
    export default{
        name:'Detail',
        components:{
            DetailBanner,
            DetailHeader,
            DetailList
        },
        data(){
            return{
                sightName:'',
                bannerImg:'',
                gallaryImgs:[],
                categoryList:[],
                }
        },
        mounted(){
            this.getDetailInfo();
        },
        methods:{
            getDetailInfo(){
                axios.get('/api/detail.json',{
                    params:{
                        id:this.$route.params.id
                    }
                })
                .then(this.getDetailInfoSucc)
            },
            getDetailInfoSucc(response){
                console.log(response);
                const res=response.data;
                if(res.ret && res.data){
                    this.sightName=res.data.sightName;
                    this.bannerImg=res.data.bannerImg;
                    this.gallaryImgs=res.data.gallaryImgs;
                    this.categoryList=res.data.categoryList;

                }
            }
        }
    }
</script>
<style>

</style>