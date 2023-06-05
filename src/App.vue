<template>
  <div>
    <h1>Rick and Morty</h1>
    <FilterByStatus/>
    <FilterByName/>
    <ListCharacters/>
  </div>
  <!-- <img alt="Vue logo" src="./assets/logo.png" class="logoHome"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
import ListCharacters from '@/components/ListCharacters.vue';
import FilterByStatus from '@/components/FilterByStatus.vue';
import FilterByName from '@/components/FilterByName.vue';
export default {
  name: 'App',
  components: {
    ListCharacters, FilterByStatus, FilterByName
  }
}
</script>

<style lang="scss">
:root{
  --background-body: #2c3e50;
  --background-card: #34495e;
  --text-gray: #bdc3c7;
  --text-orange: #e67e22;
}
body{
  font-family: sans-serif;
  background-color: var( --background-body);
}
.logoHome {
  width: 200px;
  height: 200px;
  margin: 0 auto;
  border-radius: 50%;
  display: block;
  margin-bottom: 20px;
  // border: #00ff95 1px solid;
  box-shadow:   
             -1em 0 0 7px #2c3e50a5,
             2em 0 1.5em 7px #27865b86;
}
</style>
