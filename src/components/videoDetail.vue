<template>
    <div class="videoContainer" v-if="activeVideo">
        <div>
            <iframe v-bind:src="videoUrl" frameborder="0"></iframe>
        </div>
        <div class="details">
            <h4>{{ activeVideo.snippet.title }}</h4>
            <p>{{ activeVideo.snippet.description }}</p>
        </div>
    </div>
</template>

<script>
 export default {
    name: 'videoDetail',
    props: ['activeVideo'],
    computed: {
        videoUrl() {
            const videoId = this.activeVideo.id.videoId;
            return 'https://youtube.com/embed/' + videoId;
        }
    }

 }
</script>

<style scoped>
.details {
    margin-left: 13px;
    width: 96%;
    border-radius: 20px;
    padding: 10px;
    border: 1px solid rgb(248, 244, 244);
    border-radius: 4px;
}

.videoContainer {
    display: flex;
    flex-direction: column;
    margin: auto;
    width: 50%;
    background-color: rgba(0, 0, 0, 0.877);
}

iframe {
    margin-left: 13px;
    height: 400px;
    width: 96%;
    border-radius: 20px;
}

</style>

