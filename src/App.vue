<template>
  <div id="app">
    <div class="title">
      A.I. Robot Recruiter
    </div>
    <div id="nav">
      <router-link to="/">A.I. Database</router-link> |
      <router-link to="/about">About Us</router-link>
    </div>
    <router-view/>
    <footer>
        <a href="https://github.com/tahsue/creative-project-3"> GitHub Repository </a>
    </footer>
  </div>
</template>

<style>



.title {

  font-size: 100px;
  background-color: #F2F2F2;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #F2F2F2;
}

#nav {
  width: 100%;
  margin-bottom: 50px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

footer {
  margin: 50px;
  margin-bottom: 60px;
  height: 500px;
}

a {
  text-decoration: none!important;
  font-size: 20px;
}

#nav a.router-link-exact-active {
  color: #6D97A2;
}
</style>
