<template>
    <div>
        <!-- <img :src="albumCover">
        <h2>{{ songName }}</h2>
        <h4>{{ songArtist }}</h4> -->
        <h2>{{ selection }}</h2>
        <button @click="addToSongList">Remove from playlist</button>
        <!-- <button @click="removeFromSongList">Add to Playlist</button> -->
    </div>
</template>

<script>
export default {
    name: "PlayList",
    props: {
        selection: String,
    },
    methods: {
        addToSongList() {
            this.$emit(`addToSongList`, this.selection)
        }
    },
    mounted() {
        this.selection.indexOf(this.selection);
    },
}


</script>

<style scoped>

</style>