<template>
  <ul>
      <li class="t-header">
          <p>Round</p>
          <p>Time</p>
      </li>
        <li v-for="(result, index) in resultsArr" :key="result+Math.random()">
            <p>{{index + 1}}</p>
            <p>{{result}}</p>
        </li>
  </ul>
</template>

<script>
export default {
  props:[ 'resultsArr']
}
</script>

<style scoped>
ul{
    list-style-type: none;
    display: grid;
    margin: 0 20%;
    row-gap: 5px;
    padding: 0;
}
li:nth-child(1){
    background-color:rgba(238, 174, 202, 1);
}
li{
    display: grid;
    grid-template: 1fr / 1fr 1fr;
    
    column-gap: 3px;

}
p{
    margin: 0;
    padding: 10px;
    background-color: rgba(247, 247, 247, 0.7);
     color: rgb(78, 78, 78);
}
.t-header p:nth-child(1), .t-header p:nth-child(2){
   background-color:rgba(238, 174, 202, 1); 
}

</style>