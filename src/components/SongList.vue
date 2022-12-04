<template>
    <div>
        <img :src="albumCover">
        <h2>{{ songName }}</h2>
        <h4>{{ songArtist }}</h4>
        <button @click="removeFromSongList">Add to Playlist</button>
    </div>
</template>

<script>
export default {
    name: "SongList",
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
        removeFromSongList() {
            this.$root.$emit(`removeFromSongList`, this.songName)
        }
    },
}
</script>

<style scoped>

</style>