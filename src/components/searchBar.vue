<template>
    <div>
        <form class="searchBar">
            <input @input="onInput"  placeholder="Search"/>
            <button @click="onClick" type="button"> <img src="./white-search-button.jpg" alt=""> </button>
        </form>
    </div>
</template>

<script>


export default {
    name:'searchBar',
    data() {
        return { searchWord:'' };
    },
    methods: {
        onInput(event) {
           this.searchWord = event.target.value;
            this.$emit('termChange', event.target.value);
        },
        onClick() {
            this.$emit('onClick', this.searchWord);
        }
    }
}

</script>



<style scoped>

div {
    background-color: rgba(0, 0, 0, 0);
    display: flex;
    align-items: center;
    justify-content: center;
    width: 98%;
    margin-bottom: 20px;
    margin-top: 15px;
}

form {
    height: 50px;
    width: 100%;
    max-width: 600px;
    display: flex;
    align-items: center;
    border-radius: 60px;
    padding: 8px;
    background-color: black;
}

form input {
    background: transparent;
    flex: 1;
    border: 0;
    outline: none;
    padding: 20px;
    color: white;
    font-size: 1rem;
}

::placeholder {
    color: white;
}

button {
    background-color: black;
    border: 0;
    border-radius: 50%;
    width: 39px;
    height: 39px;
    margin-bottom: 5px;
    display: flex;
    justify-content: center;
    align-items: center;
}

button img {
    border-radius: 50%;
    width: 42px;
    height: 42px;
    margin:auto;
}

button img:hover {
    cursor: pointer;
}






</style>