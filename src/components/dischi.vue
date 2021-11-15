<template>
    <div class="disks-container">
        <div class="elements" v-if="loading != true">
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
            <div class="loading-container">
                <img src="../assets/img/loading.gif" alt="">
            </div>
        </div>
    </div>    
</template>

<script>
import axios from 'axios'

export default {
    name :"dischi",

    data(){
        return{
            elements : [],
            loading: true,
        }
    },
    mounted(){
        axios
            .get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(r => {
                console.log(r.data)
                this.elements = r.data.response;
                this.loading = false 
            })
            .catch(e =>{
                console.log(e);
            })
    }
}
</script>

<style>

</style>