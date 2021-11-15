<template>
    <div class="disks-container">
        <div class="elements" v-if="this.loading != true">
            <div class="disk-container" v-for="element in elements" :key="element.name">
                <img :src="element.poster" alt="">
                <h2>{{element.title}}</h2>
                <div class="element-info">
                    <p>{{element.author}}</p>
                    <p>{{element.year}}</p>
                </div>
            </div>
        </div>    
        <div v-else class="loading" >
            <loader />
        </div>
    </div>    
</template>

<script>
import loader from './loader'
import axios from 'axios'

export default {
    name :"dischi",

    components:{
        loader,
    },

    data(){
        return{
            elements : [],
            loading: true,
        }
    },
    methods :{
        launch(){
            axios
            .get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(r => {
                console.log(r.data)
                this.elements = r.data.response;
                this.loading = false     
            })
            .catch(e =>{
                console.log(e);
            });
        }
    },


    mounted(){

        setTimeout(this.launch,2000)
        
        
    }
}
</script>

<style>

</style>