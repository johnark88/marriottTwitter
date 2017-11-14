<template>
  <div class="hello">
    <h2>Twitter App </h2>
    <button v-on:click="twitter()"></button>
  </div>
</template>

<script>
import axios from 'axios'
import twit from 'twit'

export default {
  name: 'HelloWorld',
  data: () => {
    return {
      //  Variables

    }
  },
  methods: {
      twitter: function () {
        let T = new twit({
          consumer_key:         'R4KujnUwMkxCRpUIl3QURufav',
          consumer_secret:      'vppJcsYaXBz0J14RPvkszrlZhWCyo2u9FRaQf7psGyMh6jPIZu',
          access_token:         '123084389-DrT2QHmsN12VdZvu8F5jXhv8UzGrCWyWzYevVVjL',
          access_token_secret:  'FNDgI4fJjNcItWrYHCQgAWepElfDcy5kSP9gyyBJdAhve',
      })
        T.post('statuses/update', {status: 'Batman'})
          .catch(function(err){
            console.log('error',err.stack)
          })
          .then(function(result){
            console.log('results', result.data)
          })
    //     T.post('statuses/update' , { status: 'Hello' }, function(err, data, response) {
    //         console.log(err, 'err')
    //         console.log(data, 'data')
    //         console.log(response, 'res')
    //     })
    }
  }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
