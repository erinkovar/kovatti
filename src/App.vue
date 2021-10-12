<template>
  <div class="container">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
  </div>
  
</template>

<script>
// Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
import { getAnalytics } from "firebase/analytics";
// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
// For Firebase JS SDK v7.20.0 and later, measurementId is optional
const firebaseConfig = {
  apiKey: "AIzaSyAnio6gTw_dq8xY4ax5VV3us9nikTVYhu0",
  authDomain: "kovatti-28019.firebaseapp.com",
  projectId: "kovatti-28019",
  storageBucket: "kovatti-28019.appspot.com",
  messagingSenderId: "273939693322",
  appId: "1:273939693322:web:b442860d8215352bb6c4f3",
  measurementId: "G-330CLWK39Z"
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);
const analytics = getAnalytics(app);
</script>


<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid #CCC;
  padding: 30px;
  border-radius: 3px;
}

.btn {
  display: inline-block;
  background: #222;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 3px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
