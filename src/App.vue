<template>
  <nav>
    <img src="./assets/logo.svg" alt="logo" />
    <div class="filter--search">
      <input type="text" placeholder="Input City" v-model="search" />
    </div>
  </nav>
  <div class="container">
    <div class="header">
      <h2>Stays in Finland</h2>
      <p>{{ mathcingCities.length }} stays</p>
    </div>
    <!-- stays grid -->
    <div class="stays-grid">
      <!-- each stay element -->
      <div class="stay-card" v-for="stay in mathcingCities" :key="stay.title">
        <img :src="stay.photo" alt="" />
        <div class="descriptions">
          <div class="type-rating">
            <p>{{ stay.type }}</p>
            <p class="rating">⭐ {{ stay.rating }}</p>
          </div>
          <h5>{{ stay.title }}</h5>
          <p>{{ stay.city }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import data from "./data/stays.json";

export default {
  name: "App",
  data() {
    return {
      stays: data,
      search: "",
    };
  },
  computed: {
    mathcingCities() {
      // return this.stays.filter((stay) => stay.city.includes(this.search));
      
      const { search, stays } = this
      const query = search.toLowerCase()
      if(search === '') return stays

      // return stays.filter(stay => {
      //   return Object.values(stay).some(word => String(word).toLowerCase().includes(query))
      // } )
       return stays.filter(stay => {
        return stay.city.toLowerCase().includes(query)
      } )

      // arr.filter LOOP {} => ['hel', 'country'].some (word)

    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@500;600;700&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Mulish&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: rgb(247, 243, 243);
}

nav {
  padding: 20px 60px;
  display: flex;
  justify-content: space-between;
}
.filter--search {
  padding: 10px;
  border-radius: 10px;
  box-shadow: 0px 1px 6px 0px #0000001a;
  font-family: "Mulish";
}
.filter--search input {
  border: none;
  outline: none;
  background: none;
}
.filter--search input:active {
  outline: none;
}
.filter--search input::placeholder {
  font-family: "Mulish";
}

.container {
  font-family: "Montserrat", sans-serif;
  padding-inline: 60px;
  margin-top: 30px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.stays-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 20px;
  margin-top: 20px;
}

.stays-grid img {
  width: 100%;
  height: 300px;
  border-radius: 24px;
}

@media screen and (max-width: 900px) {
  .stays-grid {
    grid-template-columns: repeat(2, 1fr);
  }

  .stays-grid img{
    height: 200px;
  }
}


@media screen and (max-width: 600px){
  nav{
    padding-inline: 20px;
  }
  .container{
    padding-inline: 20px;
  }
 .stays-grid {
    grid-template-columns: 1fr;
  }
}



.stay-card {
  transition: 0.25s all ease-in-out;
}

.stay-card:hover {
  box-shadow: 0px 1px 6px 0px #0000001a;
  border-radius: 24px;
  overflow: hidden;
}

.descriptions {
  padding: 20px;
}

.type-rating {
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
}
</style>
