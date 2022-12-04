<template>
    <!-- PARENT COMPONENT TO PLAYLIST AND SONGLIST COMPONENTS -->
    <div>
        <!-- THIS IS THE PARENT PASSING PROPS TO THE SONGLIST COMPONENT TO SHOW THEM ON THE PAGE -->
        <SongList v-for="track in tracks" :key="track.id" :songName="track.title" :songArtist="track.band"
            :albumCover="track.coverImg" @removeFromSonglist="moveToPlayList" />
        <!-- THIS IS THE PARENT PASSING PROPS TO THE PLAYLIST COMPONENT TO GET SELECTED SONGS TO APPEAR THERE -->
        <section :class="{ playlist: isAdded }">
            <PlayList v-for="track in tracks" :key="track.id" :songName="track.title" :songArtist="track.band"
                :albumCover="track.coverImg" @addToSongList="Playlist" />
        </section>
    </div>
</template>

<script>
import SongList from "@/components/SongList.vue";
import PlayList from "@/components/PlayList.vue";
export default {
    components: {
        SongList,
        PlayList
    },
    name: "PageBody",
    data() {
        return {
            isAdded: true,
            tracks: [
                {
                    id: 1,
                    title: "Never Gonna Give You Up",
                    band: "Rick Astley",
                    coverImg: "https://i.scdn.co/image/ab67616d0000b2735755e164993798e0c9ef7d7a"
                },
                {
                    id: 2,
                    title: "Heaven Is A Place On Earth",
                    band: "Belinda Carlisle",
                    coverImg: "https://upload.wikimedia.org/wikipedia/en/a/ab/Belinda_Carlisle_-_Heaven_on_Earth_cover.jpg"
                },
                {
                    id: 3,
                    title: "No Sleep Till Brooklyn",
                    band: "Beastie Boys",
                    coverImg: "https://cdns-images.dzcdn.net/images/cover/aa589618a8503edacfa8e341b1ef485c/350x350.jpg"
                },
                {
                    id: 4,
                    title: "Little Lies",
                    band: "Fleetwood Mac",
                    coverImg: "https://upload.wikimedia.org/wikipedia/en/3/3f/Little_Lies.jpg"
                },
                {
                    id: 5,
                    title: "Fast Car",
                    band: "Tracy Chapman",
                    coverImg: "https://upload.wikimedia.org/wikipedia/en/3/30/Fastcar_tchapman.jpg"
                },
            ],
            selection: []
        }
    },
    methods: {
        removeFromSonglist() {
            this.isAdded = !this.isAdded
        },
        moveToPlayList(track) {
            this.$root.$emit.selection.pop(track);
            console.log(`pop off playlist`);
        },
        Playlist(track) {
            this.selection.push(track)
            console.log(`is this on?`);
        }
    },
}

</script>

<style scoped>
.playlist {
    border: 3px solid black;
}
</style>