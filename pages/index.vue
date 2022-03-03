<template>

  <div class="container-w100">
    <div class="nav row">


<div class="col">
        <div class="logo">
            <a class="txt-logo text-decoration-none" href="#"><strong> CINO</strong>CHE </a>
            <!-- <span class="subheader">efefeefe</span> -->
          </div>
</div>
<div class="col">
            
        
    <div class="input-group">
        <input class="form-control mr-sm-2" type="search" v-model="search" placeholder="Tell me your favorite movie!" aria-label="Search">
          <span class="input-group-btn">
        <button class="btn btn-outline-warning my-2 my-sm-0" @click="moviesearch()" type="button">Go!</button>
          </span>
    </div>

            
</div>

      <!-- <button @click="moviegenre()" class="btn toggle-btn btn-outline-warning my-2 my-sm-0" >Documentary</button> -->

            <div class="links col">
            <ul class="link-grp">
                <li>
                    <a class="link-item" href="#">About us</a>
                </li>
            </ul>
            </div>
            
    </div>
    

<select name="" id="" class="categories form-control btn-outline-warning" placholder="Categories">
  <option >Categories</option>
  <option @click="moviegenreAction()">Action</option>
  <option @click="moviegenreAnimation()">Animation</option>
  <option @click="moviegenreComedy()">Comedy</option>
  <option @click="moviegenreDocumentary()">Documentary</option>
  <option @click="moviegenreHistory()">History</option>
  <option @click="moviegenreHorror()">Horror</option>
  <option @click="moviegenreScienceFiction()">Science-Fiction</option>
  <option @click="moviegenreTVmovies()">TV Movies</option>
  
</select>


<div class="container-fluid">
<div class="row">


<div id="moviec" v-for="(movie, i) in movies.results" :key="i" class="card z-depth-5 col-2">
  <img class="card-img-top" :src="'https://www.themoviedb.org/t/p/w600_and_h900_bestv2'+movie.poster_path" alt="Card image cap">
  <div class="card-body">
    <h5 class="card-title">{{movie.original_title}}</h5>
    <!-- <p class="card-text">{{movie.overview}}</p> -->
    <p>{{movie.release_date}}</p>
    <b-button v-b-modal.xxx :data-movieid="movie.id" @click="movieDetail($event)" class="btn btn-outline-warning">See more</b-button>


       
  </div>
</div>
       <b-modal id="xxx" content-class="mymodal mb-3" v-if="moviesDetail" :title="moviesDetail.original_title" :ok=btn btn-warning>
    <p class="my-4" style="background-color: rgb(12, 12, 12)!important;" >Released on :{{' '+moviesDetail.release_date}}</p>

     <div style="background-color: rgb(12, 12, 12)!important;">{{moviesDetail.overview}} 
          <img class="card-img-top" :src="'https://www.themoviedb.org/t/p/w600_and_h900_bestv2'+moviesDetail.poster_path" alt="Card image cap">
          </div>
          
  </b-modal>

  </div>
  </div>

<footer class="footer" style="background-color: darkgray!important;">
  <div class="container-fluid p-0">
    <div class="row">
      <div class="col p-0">
      <div class="footer1 pt-3">
      <h3>CINOCHE, number one on streaming</h3>
    </div>
    </div>
    </div>
    <div class="row">
      <div class="col p-0">
      <div class="footer2">
      <p>Powered by, <a href="https://www.themoviedb.org"> themoviedb.org</a></p>
    </div>
    </div>
    </div>
  </div>
</footer>




  </div>
</template>





<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital@1&family=Viaoda+Libre&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Allerta+Stencil&family=Poppins&family=Yusei+Magic&display=swap');


*{
  background-color: rgb(15, 15, 15);
 
}

::v-deep .mymodal{
background: rgb(12, 12, 12);
color: rgb(202, 185, 180);
opacity: 0.9;
font-family: 'Poppins', sans-serif;
}


.card{
  background-color: rgb(15, 15, 15);
  padding: 10px;
  margin-top: 40px;
  margin-bottom: 0;
  height: auto;
  transition: transform .3s ease; 
  border-color: rgb(31, 30, 30);
  width: 220px;
  justify-content: center;
  font-family: 'Poppins', sans-serif;
}
.card:hover{
   transform: scale(1.05);
}

.card-body{
  color: beige;
}
.nav {
    display: flex;
    height: 5rem;
    justify-content: space-between;
    align-items: center;
    /* margin-bottom: 10px; */
    font-weight: lighter;
    letter-spacing: 0.5px;
    background-color: rgb(15, 15, 15);
    /* opacity:0.2;  */
}
.nav .logo{
    
    display: flex;
    flex-direction: column;
    height: 100%;
    font-size: 50px;
    justify-content: center;
    text-decoration: none;
}

.txt-logo{
    height: 100%;
    color: rgb(255, 255, 255);
    font-family: 'Viaoda Libre', italic;
}

.input-group{
  font-family: 'Poppins', sans-serif;
}
.categories{
  font-family: 'Poppins', sans-serif;
}


.link-grp{
    list-style-type: none;
    line-height: 0;
}
.link-item{
    text-decoration: none;
    list-style: none;
    font-size: 20px;
    color: rgb(255, 255, 255);
    margin-right: 15px;
    align-items: center;
    font-family: 'Poppins', sans-serif;
    display: grid;
    justify-content: center;
}
.footer{
  background-color: darkgray;
}
.footer1 > h3{
justify-content: center;
text-align: center !important;
color: beige;

width: 100%;
font-family: 'Poppins', sans-serif;
}
.footer2 > p{
justify-content: center;
text-align: center !important;
color: beige;

width: 100%;
font-family: 'Poppins', sans-serif;
}
.footer2 > a{
justify-content: center;
text-align: center !important;
color: beige;
background-color: rgba(201, 196, 182, 0.637)!important;
width: 100%;
font-family: 'Poppins', sans-serif;
}
</style>




<script>


    export default {


       name:"mainContent",



    components:{
      
    },
    data(){
        return{
            movies:{},
            modalShow: false,
            moviesDetail:{},
        }
    },

    methods:{
        moviesearch: function(){
            fetch(
         "https://api.themoviedb.org/3/search/movie?api_key=031527da0c50b6f502203e476ecc877f&query=" +this.search
      )
        .then((response) => response.json())
        .then((data) => (this.movies = data));
        
    },

            /**Gestion detail movie */
            movieDetail: function(event){
                const idMovie = event.target.getAttribute('data-movieid');
      

                        fetch(
"https://api.themoviedb.org/3/movie/"+idMovie+"?api_key=031527da0c50b6f502203e476ecc877f"
          )
          .then((response) => response.json())
        .then((data) => (this.moviesDetail = data));

            },



            /**Fin Gestion detail movie */

        moviegenre: function(){
          fetch(
            "https://api.themoviedb.org/3/discover/movie?with_genres=99&api_key=031527da0c50b6f502203e476ecc877f&language=en-US"
          )
          .then((response) => response.json())
        .then((data) => (this.movies = data));
        },
        

      moviegenreAction: function(){
          fetch(
            "https://api.themoviedb.org/3/discover/movie?with_genres=28&api_key=031527da0c50b6f502203e476ecc877f&language=en-US"
          )
          .then((response) => response.json())
        .then((data) => (this.movies = data));
        },


        moviegenreAnimation: function(){
          fetch(
            "https://api.themoviedb.org/3/discover/movie?with_genres=16&api_key=031527da0c50b6f502203e476ecc877f&language=en-US"
          )
          .then((response) => response.json())
        .then((data) => (this.movies = data));
        },


        moviegenreComedy: function(){
          fetch(
            "https://api.themoviedb.org/3/discover/movie?with_genres=35&api_key=031527da0c50b6f502203e476ecc877f&language=en-US"
          )
          .then((response) => response.json())
        .then((data) => (this.movies = data));
        },


        moviegenreDocumentary: function(){
          fetch(
            "https://api.themoviedb.org/3/discover/movie?with_genres=99&api_key=031527da0c50b6f502203e476ecc877f&language=en-US"
          )
          .then((response) => response.json())
        .then((data) => (this.movies = data));
        },


        moviegenreHistory: function(){
          fetch(
            "https://api.themoviedb.org/3/discover/movie?with_genres=36&api_key=031527da0c50b6f502203e476ecc877f&language=en-US"
          )
          .then((response) => response.json())
        .then((data) => (this.movies = data));
        },


        moviegenreHorror: function(){
          fetch(
            "https://api.themoviedb.org/3/discover/movie?with_genres=27&api_key=031527da0c50b6f502203e476ecc877f&language=en-US"
          )
          .then((response) => response.json())
        .then((data) => (this.movies = data));
        },


        moviegenreScienceFiction: function(){
          fetch(
            "https://api.themoviedb.org/3/discover/movie?with_genres=878&api_key=031527da0c50b6f502203e476ecc877f&language=en-US"
          )
          .then((response) => response.json())
        .then((data) => (this.movies = data));
        },


        moviegenreTVmovies: function(){
          fetch(
            "https://api.themoviedb.org/3/discover/movie?with_genres=10770&api_key=031527da0c50b6f502203e476ecc877f&language=en-US"
          )
          .then((response) => response.json())
        .then((data) => (this.movies = data));
        },
        },

        async asyncData({ $http }) {
            const movies = await $http.$get(
            "https://api.themoviedb.org/3/movie/now_playing?api_key=031527da0c50b6f502203e476ecc877f"
            );
            return { movies };
            console.log(movies);
        },


    };


</script>      

   