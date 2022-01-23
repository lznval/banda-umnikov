<template>
  <div id="app">
  <Main
    v-bind:users="users"
    v-bind:beers="beers"
    @newBeer="newBeer"
  />
  </div>
</template>

<script>
import Main from '@/components/Main'
export default {
  name: 'App',
  data() {
    return {
      users: [],
      beers:[],
    }
  },
  mounted() {
    fetch('https://random-data-api.com/api/users/random_user')
        .then(response => response.json())
        .then(json => {
          this.users.push(json)
        });
    fetch('https://random-data-api.com/api/beer/random_beer')
        .then(responses => responses.json())
        .then(jsons => {
          this.beers.push(jsons)
        })
  },
  components: {
    Main
  },
  methods: {
    newBeer(id) {
      fetch('https://random-data-api.com/api/beer/random_beer')
          .then(responses => responses.json())
          .then(jsons => {
            this.beers = []
            this.beers.push(jsons)
          })
    }
  }
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
  border: 0;
}
*,*:before,*:after{
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}
body {
  background-image: url('../public/beer.jpg');
  background-repeat: no-repeat;
  background-position: 0 0;
  height: 100vh;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;

}
@media (max-width: 900px) {
  body {
    height: 100%;
  }
  #app {
    margin-top: 50px;
  }
}
</style>
