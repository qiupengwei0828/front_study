<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li>
        <a
          href="https://vuejs.org"
          target="_blank"
        >
          Core Docs
        </a>
      </li>
      <li>
        <a
          href="https://forum.vuejs.org"
          target="_blank"
        >
          Forum
        </a>
      </li>
      <li>
        <a
          href="https://chat.vuejs.org"
          target="_blank"
        >
          Community Chat
        </a>
      </li>
      <li>
        <a
          href="https://twitter.com/vuejs"
          target="_blank"
        >
          Twitter
        </a>
      </li>
      <br>
      <li>
        <a
          href="http://vuejs-templates.github.io/webpack/"
          target="_blank"
        >
          Docs for This Template
        </a>
      </li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li>
        <a
          href="http://router.vuejs.org/"
          target="_blank"
        >
          vue-router
        </a>
      </li>
      <li>
        <a
          href="http://vuex.vuejs.org/"
          target="_blank"
        >
          vuex
        </a>
      </li>
      <li>
        <a
          href="http://vue-loader.vuejs.org/"
          target="_blank"
        >
          vue-loader
        </a>
      </li>
      <li>
        <a
          href="https://github.com/vuejs/awesome-vue"
          target="_blank"
        >
          awesome-vue
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
//import main from '../main.js'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  mounted(){
    //this.testGetBackPathVariable();
    console.log("11111111111111111111111111111");
    let arr=['1','2','3','4','5'];
    this.testGetParams();
    var arrStr=arr.join();
    console.log(arrStr);
  },
  methods:{
     /**
      *测试前端跨域请求
      */
     testCros: function(){
        axios
        .get('/try/ajax/json_demo.json')
        .then(function(response){
         console.log(response.data);
        }  
        )
        .catch(function (error) { // 请求失败处理
         console.log(error);
       });
     },
     /**
      * 测试 pathVariable
      */
     testGetBackPathVariable:function(){
       axios.get('/testStudy/v1/item/itemIndex').then(function(response){
       console.log(response);
       }).catch(function(error){
       console.log(error);
       });
     },
     /**
      * 测试 pathParams
      */
     testGetParams:function(){
       //console.log(main);
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
