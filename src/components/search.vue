<template>
    <div class="filter-container">
        <label for="selection">Choose a gender</label>
        <select name="selection" v-model="selection" @change="$emit('search',selection)">
            <option value="">All</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
        <label for="albums">Choose an artist</label>
        <select name="albums" v-model="artist" @change="$emit('searchArtist',artist)">
            <option value="">All</option>
            <option value="Bon Jovi">Bon Jovi</option>
            <option value="Queen">Queen</option>
            <option value="Sting">Sting</option>
            <option value="Steve Gadd Band">Steve Gadd Band</option>
            <option value="Iron Maiden">Iron Maiden</option>
            <option value="Eric Clapton">Eric Clapton</option>
            <option value="Deep Purple">Deep Purple</option>
            <option value="Metallica">Metallica</option>
            <option value="Dave Weckl">Dave Weckl</option>
            <option value="Michael Jacjson">Michael Jacjson</option>
        </select>
    </div>
</template>

<script>
export default {
    name : "search",
    data (){
        return {
            selection: "",
            artist: ""
        }
    }
}
</script>

<style>

</style>