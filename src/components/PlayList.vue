<template>
    <div>
        <img :src="albumCover">
        <h2>{{ songName }}</h2>
        <h4>{{ songArtist }}</h4>
        <button @click="addToSongList">Remove from playlist</button>
    </div>
</template>

<script>
export default {
    name: "PlayList",
    props: {
        songNumber: Number,
        songName: String,
        songArtist: String,
        albumCover: {
            type: String,
            default: "https://www.edigitalagency.com.au/wp-content/uploads/Spotify-Icon-png-rgb-black.png"
        }
    },
    methods: {
        addToSongList() {
            this.$emit(`addToSongList`, this.songName)
        }
    },
}
</script>

<style scoped>

</style>