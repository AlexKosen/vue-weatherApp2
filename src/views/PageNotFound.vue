<script setup>
import TheFooter from "../components/TheFooter.vue";
</script>


<template>
  <div class="site-content">
    <div class="site-header">
      <div class="container">
        <RouterLink v-bind:to="{ name: 'home' }" class="branding">
          <img src="@/assets/images/logo.png" alt="" class="logo" />
          <div class="logo-type">
            <h1 class="site-title">Company name</h1>
            <small class="site-description">tagline goes here</small>
          </div>
        </RouterLink>
      </div>
      <div class="container-inner">
        <div class="inner">
          <h2>404</h2>
          <p>Page not found</p>
          <p>
            <button class="btn">
              <RouterLink v-bind:to="{ name: 'home' }"
                >Back to home
              </RouterLink>
            </button>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container-inner {
  display: flex;
  height: 100vh;
}
.inner {
  margin: auto;
}
h2 {
  font-size: 130px;
  letter-spacing: 20px;
  margin: 20px;
}
p {
  font-size: 18px;
  text-align: center;
}
a {
  text-decoration: none;
  color: #bfc1c8;
}
.btn {
  color: #bfc1c8;
  padding: 10px 25px;
  border: #1e202b;
  border: 2px solid;
  border-radius: 30px;
  -webkit-transition: 0.3s ease;
  transition: 0.3s ease;
  font-weight: 400;
  font-size: 14px;
  background-color: #1e202b;
}
 .btn:hover a, .btn:hover{
  border-color: #009ad8;
  color: #009ad8;
}
</style>