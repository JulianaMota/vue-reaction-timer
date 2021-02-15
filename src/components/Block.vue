<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
      click me!!
  </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return{
            showBlock: false,
            timer: null,
            reactionTime: 0
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
        }, this.delay);
    },
    methods:{
        startTimer(){
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10);
        },
        stopTimer(){
            clearInterval(this.timer)
            console.log(this.reactionTime)
            this.$emit('end', this.reactionTime)
        }
    }

}
</script>

<style>
.block{
    width: 400px;
    border-radius: 20px;
    background: #fdfdfd;
    color: rgb(190, 39, 145);
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
    font-weight: bolder;
    font-size: 20px;
    box-shadow: 1px 1px 15px 1px #000;
    font-style: italic;
    text-transform: uppercase;
}
</style>