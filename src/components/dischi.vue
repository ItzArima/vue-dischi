<template>
    <div class="element">
        <div class="disc-container" v-for="element in elements" :key="element.name">
            <img :src="element.poster" alt="">
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
        }
    },
    mounted(){
        axios
            .get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(r => {
                console.log(r.data)
                this.elements = r.data.response;
            })
            .catch(e =>{
                console.log(e);
            })
    }
}
</script>

<style>

</style>