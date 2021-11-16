<template>
    <div class="filter-container">
        <label for="selection">Choose a gender</label>
        <select name="selection" v-model="selection">
            <option value="All">All</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
        <button @click="$emit('search',selection)">Search</button>
    </div>
</template>

<script>
export default {
    name : "search",
    data (){
        return {
            selection: "All"
        }
    }
}
</script>

<style>

</style>