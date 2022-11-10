<template>
    <li @click="onVideoSelect">
        <img :src="thumbnail" />
        <div> {{ videoTitle }} </div>
    </li>
</template>

<script>
export default {
    name: 'videoListItems',
    props: ['video'],
    computed: {
        thumbnail() {
            return this.video.snippet.thumbnails.default.url;
        },
        videoTitle() {
            return this.video.snippet.title;
        }
    },
    methods: {
        onVideoSelect() {
            this.$emit('videoSelect', this.video);
        }
    }
}
</script>



<style scoped>
li {
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    justify-content: flex-start;
    padding: 0.3rem;
    background-color: rgb(15, 15, 15);
    border-radius: 20px;
    margin: 5px;
}

li:hover {
    background-color: rgb(84, 82, 82);
    cursor: pointer;
}

img {
    border-radius: 15px;
}

div{
    margin-left: 15px;
}





</style>