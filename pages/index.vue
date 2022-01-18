<template>
  <div class="container-fluid">
<div class="row">

<div v-for="(movie, i) in movies.results" :key="i" class="card" style="width: 18rem;">
  <img class="card-img-top" :src="'https://www.themoviedb.org/t/p/w600_and_h900_bestv2'+movie.poster_path" alt="Card image cap">
  <div class="card-body">
    <h5 class="card-title">{{movie.original_title}}</h5>
    <p class="card-text">{{movie.overview}}</p>
    <p>{{movie.release_date}}</p>
    <a href="#" :id="movie.id" class="btn btn-primary">See more</a>
  </div>
</div>


</div>

  </div>
</template>





<style scoped>
*{
  background-color: black;
}
.card{
  background-color: beige;
  margin: 10px;
  margin-top: 40px;
  transition: transform .2s; 
  align-items: center;
  justify-content: center;
  color: beige;
}
.card:hover{
   transform: scale(1.1);
}


.card-text{
  color: beige;
}
</style>




<script>

    export default {

        async asyncData({ $http }) {
            const movies = await $http.$get(
            "https://api.themoviedb.org/3/movie/now_playing?api_key=031527da0c50b6f502203e476ecc877f"
            );
            return { movies };
            console.log(movies);
        },

    };

</script>      

    