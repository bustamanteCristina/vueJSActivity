<template>
  <div id="background" style="padding-top:20px;">
    <center>
      <div class="div1">
      <div id="divLogin" >
        <form class="container">
          <center>
            <h1>Login</h1>
          </center>
          <hr>
          <div class="row">
            <label id="username" for="loginUsername">Username:</label>
            <input
              required
              v-model="username"
              name="username"
              class="form-control"
              placeholder="Enter Username"
            > 
            <br>
          </div>
          <br>
          <div class="row">
            <label id="pass" for="loginPassword">Password:</label>
            <input
              required
              v-model="password"
              type="password"
              name="password"
              class="form-control"
              id="loginPassword"
              placeholder="Enter Password"
            >
          </div>
          <br>
          <button id="btnLogin" class="btn btn-outline-primary" @click="submit">
            <h6>Login</h6>
          </button>
          <br><br>
        </form>
      </div>
      <h2 class="text">Easakay</h2>
      </div>
    </center>
  </div>

</template>
<style scoped lang="scss">
@import "assets/style.scss";

#username {
  color: $black !important;
}
#pass {
  color: $black !important;
}
.div1 {
  width: 1000px;
  height: 600px;  
  padding: 50px;
  border: 1px solid green;
  background-color: green;
}
#divLogin {
  border-top-left-radius: 100px;
  border-bottom-left-radius: 100px;
  width: 600px;
  height: 400px;  
  padding: 50px;
  border: 1px solid green;
  background-color:white;
  margin-left: 250px;
}
.text {
  float: left;
  color : $white !important;
  
}

</style>
<script>

import AUTH from 'services/auth'
import jquery from "jquery";
export default {
  data() {
    AUTH
    return {
      username: "",
      password: ""
    };
  },
  methods: {
    submit: function(e) {
      e.preventDefault();
      AUTH.login(this.username, this.password)
  
      let link= `http://localhost:3000/db/retrieve/${this.username}/${this.password}`;
      jquery
        .ajax({
          url: link,
          method: 'GET',
          headers: {
            'Access-Control-Allow-Origin': '*'
          }
        })
        .then(response => {
          alert(response.username);
        })
       
  }

  }
};
</script>