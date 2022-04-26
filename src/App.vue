<template>
  <div id="app">
    <Main />
  </div>
</template>

<script>
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Main
  }
}
</script>

<style lang="scss">
/* width */
::-webkit-scrollbar {
  width: 10px;
}

/* Track */
::-webkit-scrollbar-track {
  background: black;
  box-shadow: inset 0 0 5px white; 
  border-radius: 0;
  margin-block: -10px;

}
 
/* Handle */
::-webkit-scrollbar-thumb {
  border-radius: 10px;
  transition: all 1s ease;
  background: cornflowerblue;

}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  border-radius: 10px;
  background: #3fb984;
}
</style>
