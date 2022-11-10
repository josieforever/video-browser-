<template>
    <li>
        <img :src="thumbnail" />
        <div> {{ videoTitle }} </div>
    </li>

</template>

<script>

export default {
    name:'autoGenerateItems',
    props: ['onevideo'],
    computed: {
        thumbnail() {
            return this.onevideo.snippet.thumbnails.medium.url;
        },
        videoTitle() {
            return this.onevideo.snippet.title;
        }
    }
}

</script>

<style scoped>

li {
    width: 98%;
    text-decoration: none;
    list-style: none;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

img {
    border-radius: 10px;
    height: 10rem;
    width: 17rem;
    margin-bottom: 13px;
}

div {
    background-color: rgb(74, 74, 74);
    font-size: 0.8rem;
    height: 45px;
    width: 250px;
    border-radius: 5px;
    text-align: center;
    color: white;
    padding: 0.1rem;
}

</style>

