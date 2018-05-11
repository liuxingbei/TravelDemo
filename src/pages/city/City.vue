<template>  
    <div>
            <city-header></city-header>
            <city-search :cities="cities"></city-search>
            <city-list :cities="cities" :hotCities="hotCities" :letter="letter"></city-list>
            <city-alphabet :list="cities" @change="handleLetterChange"></city-alphabet>
    </div> 
    

</template>
<script>
    import CityHeader from './components/Header.vue'
    import CitySearch from './components/Search.vue'
    import CityList from './components/List.vue'
    import CityAlphabet from './components/Alphabet.vue'
    import axios from 'axios'
    export default{
        name:'City',
        components:{
            CityHeader,
            CitySearch,
            CityList,
            CityAlphabet
        },
        data(){
            return{
cities:{},
hotCities:[],
letter:''
            }
        },
        mounted(){
            this.getCityInfo();
        },
        methods:{
            getCityInfo(){
                axios.get('/api/city.json')
                .then(this.getCityInfoSucc)
            },
            getCityInfoSucc(response){
                
                let res=response.data;
                if(res.ret && res.data){
                    this.cities=res.data.cities;
                    this.hotCities=res.data.hotCities;
                }
            },
            handleLetterChange(letter){
                this.letter=letter;
            }

        }
    }
</script>
<style></style>