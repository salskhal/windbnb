<template>
  <nav>
    <img src="./assets/logo.svg" alt="logo">
    <div class="filter--search">
      <input type="text" placeholder="Input City">
    </div>
  </nav>
  <div class="container">
    <div class="header">
      <h2>Stays in Finland</h2>
      <p>12+ stays</p>
    </div>
    <div class="stays-grid">
      <div class="stay-card">
        <img src="https://images.unsplash.com/photo-1505873242700-f289a29e1e0f?ixlib=rb-1.2.1&auto=format&fit=crop&w=2255&q=80" alt="">
        <div class="descriptions">
          <div class="type-rating">
            <p>Entire Apartment</p>
            <p class="rating">⭐ 4.40</p>
          </div>
          <h5>Lovely Studio near Railway Station</h5>
        </div>
      </div>
      <div class="stay-card">
        <img src="https://images.unsplash.com/photo-1505873242700-f289a29e1e0f?ixlib=rb-1.2.1&auto=format&fit=crop&w=2255&q=80" alt="">
        <div class="descriptions">
          <div class="type-rating">
            <p>Entire Apartment</p>
            <p class="rating">⭐ 4.40</p>
          </div>
          <h5>Lovely Studio near Railway Station</h5>
        </div>
      </div>
      <div class="stay-card">
        <img src="https://images.unsplash.com/photo-1505873242700-f289a29e1e0f?ixlib=rb-1.2.1&auto=format&fit=crop&w=2255&q=80" alt="">
        <div class="descriptions">
          <div class="type-rating">
            <p>Entire Apartment</p>
            <p class="rating">⭐ 4.40</p>
          </div>
          <h5>Lovely Studio near Railway Station</h5>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@500;600;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Mulish&display=swap');
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

nav{
  padding: 20px 60px;
  display: flex;
  justify-content: space-between;
  
}
.filter--search{
  padding: 10px;
  border-radius: 10px;
  box-shadow: 0px 1px 6px 0px #0000001A;
  font-family: "Mulish";
}
.filter--search input{
  border: none;
  outline: none;
}
.filter--search input:active{
  outline: none;
}
.filter--search input::placeholder{
  font-family: "Mulish";
}

.container{
  font-family: "Montserrat", sans-serif;
  padding-inline: 60px;
  margin-top: 30px;
}

.header{
  display: flex;
  justify-content: space-between;
  align-items: center;
}


.stays-grid{
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 20px;
  margin-top: 20px;
}

.stays-grid img{
  width: 100%;
  border-radius: 24px;
}


.stay-card{
  transition: .25s all ease-in-out;
}

.stay-card:hover{
   box-shadow: 0px 1px 6px 0px #0000001A;
   border-radius: 24px;
   overflow: hidden;
}

.descriptions{
  padding: 20px;
}

.type-rating{
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
}
</style>
