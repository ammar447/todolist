<template>
  <div id="app">
    <div class="all">
      <br />
      <div class="log">
        <form>
          <h1 class="h1">LOG IN</h1>
          <hr class="h" />
          <p>User name</p>
          <input type="text" placeholder="user name" v-model="login.name" />
          <p>password</p>
          <input type="password" placeholder="password" v-model="login.password" />
          <br />
         
          
        </form>
        <!--start footer-->
         <button class="s" @click.prevent="log" > logIn</button>
        <!--end footer-->
      </div>
    </div>
  </div>
</template>

<script>
 import Axios from 'axios';
export default {
  name: "App",
  components: {},
  data: function() {
    return {
      login: {
        name: "",
        password: "",
      },
    };
  },
  methods: {
    log: function() {
   Axios.post('https://login-7be8f.firebaseio.com/log.json', this.login);
     console.log('done');
            let route = this.$router.resolve({ path: "/todo"});
      // let route = this.$router.resolve('/link/to/page'); // This also works.
      window.open(route.href, '_blank');
    } ,
    
   
    
    
  },
  
 
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Lato:ital@1&display=swap");

.all {
  background-image: url(../assets/1.jpg);
  width: 100%;
  height: 657px;
  background-size: cover;
  font-family: "Lato", sans-serif;
}
.log {
  margin-left: 100px;
  margin-top: 40px;
  width: 300px;
  background-color: rgb(104, 111, 121, 0.4);
  text-align: center;
  height: 435px;
  border-radius: 5%;
}
.log .h {
  width: 170px;
  height: 1px;
  background-color: #ddd;
  /* border-radius: 75%; */
  margin-left: 60px;
}
.log .h1 {
  padding-top: 20px;
}
.log p {
  padding-bottom: 7px;
  font-size: 25px;
}

.log input {
  padding: 7px;
  border-radius: 5%;
}
.log .s {
  margin-top: 40px;
  background: none;
  font-size: 20px;
  font-family: "Lato", sans-serif;
}
/*start footer  

    this.blog.name = "";
      this.blog.password = "";
      this.$router.push({ path: "/todo" });
      */

/*end footer*/
</style>
