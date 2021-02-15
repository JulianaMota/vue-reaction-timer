<template>
  <p >Reaction time: {{ score }} ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
    props:[ 'score'],
    data(){
        return{
            rank: null
        }
    },
    mounted(){
        if(this.score < 250){
            this.rank = "Ninja Fingers!"
        } else if(this.score < 400){
            this.rank = 'Rapid Reflexes!'
        }else{
            this.rank = 'Snail pace...'
        }
    }
}
</script>

<style>
    p{
        color: rgb(78, 78, 78);
        font-weight: bold;
        padding: 20px 0;
    }
    .rank{
        color: rgb(55, 107, 167);
        font-size: 25px;
        border-bottom: 5px solid rgb(55, 107, 167);
        margin: 5% 20%;
    }
</style>