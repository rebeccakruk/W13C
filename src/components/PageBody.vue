<template>
    <!-- PARENT COMPONENT TO PLAYLIST AND SONGLIST COMPONENTS -->
    <div>
        <h1>Hits of 1987!</h1>
        <!-- THIS IS THE PARENT PASSING PROPS TO THE SONGLIST COMPONENT TO SHOW THEM ON THE PAGE -->
        <SongList v-for="track in tracks" :key="track.id" :songName="track.title" :songArtist="track.band"
            :albumCover="track.coverImg" @removeFromSongList="addToPlaylist" />
        <!-- THIS IS THE PARENT PASSING PROPS TO THE PLAYLIST COMPONENT TO GET SELECTED SONGS TO APPEAR THERE -->
        <section :class="{ playlist: isAdded }">
            <h2>Playlist</h2>
            <PlayList customString="Playlist" ref="selection" v-bind:selection="selection"
                v-for="(selection, index) in selection" :key="index" @addToSongList="removeFromPlaylist" />
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
            isNotAdded: true,
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
            selection: [],
        }
    },
    methods: {
        addToPlaylist(selection) {
            this.$refs[`selection`];
            console.log(selection);
            this.isAdded != this.isAdded;
            this.selection.push(selection);
        },
        clearSongList(selection) {
            this.selection.indexOf(selection);
            this.selection.splice(this.selection.indexOf(selection), 1);
        },
        removeFromPlaylist(selection) {
            console.log(`remove song`, selection);
            this.selection.pop(selection);
        }
    },
    mounted() {
        const selection = [];
        this.selection.indexOf(selection);
        this.selection.splice(this.selection.indexOf(selection), 1);
    },
}


</script>

<style scoped>
.playlist {
    border: 3px solid black;
    width: 50vw;
    position: relative;
    left: 50%;
    transform: translateX(-50%);
    background-color: lightskyblue;
}
</style>