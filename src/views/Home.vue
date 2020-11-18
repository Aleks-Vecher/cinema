<template>
  <div class="home">
    <h1>{{hello}}</h1>
    <Slider :popular="popular"/>
  </div>
</template>

<script>
import server from "@/assets/libs/server";


// components
import Slider from "@/components/Slider";


export default {
  name: 'Home',
  data(){
    return {
      hello: "Hello world",
popular: []
    }
  },
  created(){

    server('popular')
        .then(data => {
          this.popular = data.results.slice(0, 5);
        })
  },
  mounted(){
    // console.log(1);
    this.hello = 'hello guys'
  },
  beforeUpdate(){
    // console.log(2)
  },
  updated(){
    // console.log(3)
  },
  components: { Slider }
}
</script>
