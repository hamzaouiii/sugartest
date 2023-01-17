<template>
  <div class="hello">
    {{ requestData }}
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'HelloWorld',
  data() {
    return{    requestData: null}
  },
  methods: {
    runTest(){
      axios.get('https://stebdemo.crmhosting4u.com/rest/v11/Contacts',{
        headers: {
          'oauth-token' : '99793967-1110-43ab-954c-6e300b04d49b',
          'content-type': 'application/json'
        }
      }).then( response => {
        this.requestData = response.data;
        console.log(response.data);
      })
      .catch((error) =>  {
        this.requestData = error;
        console.log(error);
    })
   
  }
  },
  mounted() {
    this.runTest();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
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
