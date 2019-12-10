<template>
  <div class="hello">
    <div class="HelloWorld">
       <button class="allButton" v-on:click='changeColor("")'>all</button>
         <button class="redButton" v-on:click='changeColor("red")'>Red</button>
         <button class="blueButton" v-on:click='changeColor("blue")'>Blue</button>
         <button class="yellowButton" v-on:click='changeColor("yellow")'>Yellow</button>
         <button class="purpleButton" v-on:click='changeColor("purple")'>Purple</button>
    <div v-for="item in ifColor" 
    :key="item.id">
    <div class="items" >
    <p>The color is: {{item.color}}</p>
    <p>The price is: {{item.price}}</p>
    </div>
   
    </div>
  </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
  },
  data: function(){
    return{
      list: [
    {    id : 1,
        color : "red",
        price : 500
    },
    {    id : 2,
        color : "green",
        price : 200
    },
    {    id : 3,
        color : "blue",
        price : 700
    },{
        id : 4,
        color : "yellow",
        price : 800
    },
    {    id : 5,
        color : "purple",
        price : 1000
    }],
    ifColor : ''
    }
  },
  methods:{
    changeColor(e){
      this.ifColor = this.list;
    this.ifColor.filter(i => i.color= e.value)
      
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.items{
   display: inline-block;
    width:300px;
    height: 300px;
    background-color: cadetblue;
    margin: 10px;
}
.redButton{
    background-color: lightcoral;
    color: rgb(124, 3, 3);
}
.blueButton{
    background-color:lightskyblue;
    color:blue;
}
.yellowButton{
    background-color: burlywood;
    color: yellow;
}
.purpleButton{
background-color: rgb(182, 139, 204);
color: blueviolet;
}
.greenButton{
background-color: chartreuse;
color: green;
}
button{
    border-radius: 45%;
    width: 150px;
    height: 70px;
    float: left;
    margin: 0px;
   
}
</style>
