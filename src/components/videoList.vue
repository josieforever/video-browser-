<template>
    <ul>
        <videoListItems :video="oneVideo" v-for="oneVideo in youtubeVideos" :key="oneVideo.etag" @videoSelect="onVideoSelect"></videoListItems>
    </ul>
</template>

<script>

import videoListItems from './videoListItems.vue';

export default {
    name:'videoList',
    props: ['youtubeVideos'],
    components: {
        
        videoListItems,
    },
    methods: {
        onVideoSelect(video) {
            this.$emit('videoSelect', video)
        }
    }
}
</script>

<style scoped>

ul {
    padding: 0.5rem;
    width: 50%;
    background-color: coral;
    background-color:rgba(0, 0, 0, 0.877);
}

</style>