<template>
    <div id="app" class="container">
        <searchBar  @onClick="onTermChange"></searchBar>
        <autoGenerate @ready="beforeVideoDisplay"  :autogeneratevideos="autoGenerateVideos"></autoGenerate>
        <div class="innerContainer">
            <videoList v-bind:youtubeVideos="videos"  @videoSelect="onVideoSelect" ></videoList>
            <videoDetail v-bind:activeVideo="selectedVideo">  </videoDetail>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    import searchBar from './components/searchBar';
    import autoGenerate from './components/autoGenerate';
    import videoList from './components/videoList';
    import videoDetail from './components/videoDetail';
    //API's
    const API_KEY1 = 'AIzaSyAVzMi1828YobZY40XsLCzW_PPysfI4f9c';
    const API_KEY2 = 'AIzaSyAVzMi1828YobZY40XsLCzW_PPysfI4f9c';


    export default {
        name:'App',
        components: {
            searchBar,
            autoGenerate,
            videoList,
            videoDetail,
        },
        data() {
            return { autoGenerateVideos: [], videos: [], selectedVideo: null, };
        },
        methods: {
            beforeVideoDisplay(searchTerm1) {
                axios.get('https://www.googleapis.com/youtube/v3/search', {
                    params:{
                        key: API_KEY1,
                        type: 'video',
                        part:'snippet',
                        q: searchTerm1
                    }
                }).then(response => { this.autoGenerateVideos = response.data.items })
            },
            onVideoSelect(video) {
                this.selectedVideo = video;
            },
            onTermChange(searchTerm2){
                axios.get('https://www.googleapis.com/youtube/v3/search', {
                params: {
                    key: API_KEY2,
                    type: 'video',
                    part: 'snippet',
                    q: searchTerm2
        }
    }).then(response => { this.videos = response.data.items; })
            }
        }
    };

</script>{

<style scoped>

.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.innerContainer {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    background-color: rgba(0, 0, 0, 0.877);
    width: 98%;
}

</style>>


