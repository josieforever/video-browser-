<template>
    <ul>
        <autoGenerateItems  v-for="oneVideo in autogeneratevideos" :onevideo="oneVideo" :key="oneVideo.etag"></autoGenerateItems>
        
    </ul>
</template>

<script>

import autoGenerateItems from './autoGenerateItems.vue';

export default {
    name:'autoGenerate',
    created() {
        const autoGenerateArray = ["carwow","donut media","throttle hosue","top gear"," dave gray"];
        const searchTerm1 = autoGenerateArray[Math.floor( Math.random() * 5 )]; 
        this.$emit('ready', searchTerm1);
    },
    props: ['autogeneratevideos'],
    methods: {},
    components: {
        autoGenerateItems,
    }
};
</script>

<style scoped>
ul {
    height: 250px;
    width: 98%;
    background-color: black;
    border-radius: 10px;
    display: flex;
    flex-direction: row ;
    justify-content: space-evenly;
    align-items: center;
}
</style>