<template>
 <div>
   <section class="slider" v-for="movie in popular">
     <img :src="'https://image.tmdb.org/t/p/original/' + movie.backdrop_path" alt="">

       <article class="slider-desc">
         <div class="container">

           <h1>{{movie.title}}</h1>
           <p class="desc">{{ movie.overview }}</p>

         </div>

       </article>



   </section>
 </div>
</template>

<script>
export default {
name: "Slider",
  props: ['popular']
}
</script>

<style lang="scss">
@import 'src/assets/styles/main';
.slider{
  position: relative;
  .slider-desc{
    background: $black;
    background: -moz-linear-gradient(top,  rgba($white,0) 0%, rgba($black,1) 100%);
    background: -webkit-linear-gradient(top,  rgba($white,0) 0%,rgba($black,1) 100%);
    background: linear-gradient(to bottom,  rgba($white,0) 0%,rgba($black,1) 100%);
    position: absolute;
    right: 0;
    left: 0;
    bottom: 0;
    color: $white;
    padding: 10px 0px;
  }
}
</style>