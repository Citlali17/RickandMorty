<template>
    <div>
        <h1>The Rick and Morty Charactors</h1>
        <div class="main-container">
        <div v-for="character in charactors.results" :key="character.id">
            <div class="second-container">
                <h1>{{ character.name }}</h1>
                <img :src="character.image" alt="">
            </div>
        </div>
    </div>
    </div>
</template>

<script>
export default{
    name:"rickAndMorty",
    data(){
        return{
        charactors:[]
        }
    },
    methods: {
        callingAPI(){
            fetch("https://rickandmortyapi.com/api/character").then(res => res.json().then((data) => {
            this.charactors=data
            }))
        }
    },
    mounted() {
        this.callingAPI()
    }
}
</script>

<style scoped>
    .main-container {
        margin: 0 auto;
        width: 1200px;
        font-family: sans-serif;
        font-size: 40px;
        background: gray;
        display: flex;
        flex-wrap: wrap;
        text-align: center;
        justify-content: center;
        
    }

    .second-container {
        width: 500px;
        font-size: medium;
        color:aliceblue;
        background-color: rgb(53, 53, 53);
        display: flex;
        flex-wrap: wrap;
        justify-content: center;

    }

    h1{
        margin: 0 auto;
        display: flex;
        justify-content: center;
        text-align: center;
        align-items: center;
        height: 120px;
        font-size: small;
        

    }


</style>

















