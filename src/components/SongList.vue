<template>
    <div class="songList">
        <img :src="albumCover">
        <h2>{{ songName }}</h2>
        <h4>{{ songArtist }}</h4>
        <div>
            <button @click="removeFromSongList">Add to Playlist</button>
        </div>
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
            default: ""
        }
    },
    methods: {
        removeFromSongList() {
            this.$emit(`removeFromSongList`, this.songName);
            // this.$emit(`removeFromSongList`, this.songNumber);
            // this.$emit(`removeFromSongList`, this.songArtist);
            // this.$emit(`removeFromSongList`, this.albumCover)
        }
    },
}
</script>

<style scoped>
.songList {
    background-color: bisque;
    display: grid;
    grid-auto-rows: 25%;
    border: 3px solid black;
    height: 20vh;
    border: 3px solid black;
    width: 80vw;
    position: relative;
    left: 50%;
    transform: translateX(-50%);
}

img {
    height: 20vh;
}
</style>