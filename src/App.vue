<script setup>
import Phone from './components/Phone.vue'
</script>

<template>
    <div class="home">
      <Phone class="phone" />
      <div class="description">
        <h1>iMate</h1>
        <p class="desc">Not just any mood tracker, but one which aids you towards understanding and bettering your emotional well-being.</p>
        <a class="button" href="/imate.apk">Download the APK now</a>
      </div>
    </div>
</template>

<style scoped>
.home {
  display: grid;
  grid-template-columns: 1fr 1fr;
  background: url("/iMate.jpg") no-repeat center center fixed;
  place-items: center;
  align-items: center;
  height: 96vh;
}

.description {
  display: flex;
  flex-direction: column;
  background-color: rgba(0, 0, 0, 0.829);
  padding: 5rem;
}

.desc {
  width: 60%;
  text-align: justify;
  line-height: 1.8;
}

.button {
  width: 200px;
  padding: 1rem 1.5rem;
  color: rgb(206, 206, 31);
  background-color: black;
  border-radius: 20px;
  border: 2px solid rgb(206, 206, 31);
  font-family: "Montserrat", sans-serif;
  margin-top: 20px;
  margin-bottom: 25px;
  text-decoration: none;
  transition: transform 0.3s;
}

.button:hover {
  transform: translateY(-10px);  
}

h1 {
    font-family: "Rubik", sans-serif;
    font-optical-sizing: auto;
    font-weight: 700;
    font-style: normal;
    font-size: 5rem;
    margin: 0;
}

@media screen and (max-width: 768px){
  .home {
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 1fr;
    height: 100vh;
    overflow-y: hidden;
  }
  .description {
    grid-row: 1 / 2;
    text-align: center;
    justify-content: center;
    align-items: center;
    padding: 0;
    background-color: transparent;
    margin-bottom: 3rem;
    margin-top: 2rem; 
  }
  .phone {
    grid-row: 2 / 3;
  }
}

</style>