<template>
    <div class="disc-container">
        <img :src="elements.poster" alt="">
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
                this.elements = r.data,
                console.log(this.elements);
            })
            .catch(e =>{
                console.log(e);
            })
    }
}
</script>

<style>

</style>