<template>
  <div class="hello">
    <hr/>
    <h2>Test api call</h2>
    <div>{{ hello }}</div>
    <hr/>
    <div>
        <h2>Test video api call</h2>
        <div v-for="item in video" :key="item.id">
          {{ item.id }} - {{ item.desc }}
        </div>
    </div>
    <hr/>
    <h1>{{ msg }}</h1>
    
  </div>
</template>

<script>
import gql from 'graphql-tag'

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  apollo: {
    // Simple query that will update the 'hello' vue property
    hello: gql`query {
      hello
    }`,
    video: gql`query videoList {
      video {
        id,
        tiktok_id,
        desc
      }
    }`,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
