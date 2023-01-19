<script setup>
import TheFooter from '../components/TheFooter.vue';
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
        <!-- Default snippet for navigation -->
        <div class="main-navigation">
          <button type="button" class="menu-toggle">
            <i class="fa fa-bars"></i>
          </button>
          <ul class="menu">
            <li class="menu-item">
              <RouterLink v-bind:to="{ name: 'home' }">Home</RouterLink>
            </li>
            <li class="menu-item">
              <RouterLink v-bind:to="{ name: 'news' }">News</RouterLink>
            </li>
            <li class="menu-item current-menu-item">
              <RouterLink :to="{ name: 'live-cameras' }"
                >Live cameras</RouterLink
              >
            </li>
            <li class="menu-item">
              <RouterLink :to="{ name: 'photos' }">Photos</RouterLink>
            </li>
            <li class="menu-item">
              <RouterLink :to="{ name: 'contact' }">Contact</RouterLink>
            </li>
          </ul>
          <!-- .menu -->
        </div>
        <!-- .main-navigation -->

        <div class="mobile-navigation"></div>
      </div>
    </div>
    <!-- .site-header -->

    <main class="main-content">
      <div class="container">
        <div class="breadcrumb">
            <RouterLink v-bind:to="{ name: 'home' }">Home</RouterLink>
          <span>Live cameras</span>
        </div>
      </div>

      <div class="fullwidth-block">
        <div class="container">
          <div class="filter">
            <div class="country filter-control">
              <label for="">Country</label>
              <span class="select control">
                <select name="" id="">
                  <option value="">All Countries</option>
                </select>
              </span>
            </div>
            <div class="count filter-control">
              <label for="">Show per page</label>
              <span class="select control">
                <select name="" id="">
                  <option value="">1</option>
                  <option value="">2</option>
                  <option value="">3</option>
                  <option value="">4</option>
                  <option value="">5</option>
                  <option value="">6</option>
                  <option value="">7</option>
                  <option value="">8</option>
                  <option value="">9</option>
                  <option value="">10</option>
                </select>
              </span>
            </div>
            <div class="quality filter-control">
              <label for="">Only high quality</label>
              <span class="select control">
                <select name="" id="">
                  <option value="">Yes</option>
                  <option value="">No</option>
                </select>
              </span>
            </div>
          </div>
          <div class="row">
            <div class="col-md-3 col-sm-6">
              <div class="live-camera">
                <figure class="live-camera-cover">
                  <img src="@/assets/images/live-camera-1.jpg" alt="" />
                </figure>
                <h3 class="location">New York</h3>
                <small class="date">8 oct, 8:00AM</small>
              </div>
            </div>
            <div class="col-md-3 col-sm-6">
              <div class="live-camera">
                <figure class="live-camera-cover">
                  <img src="@/assets/images/live-camera-2.jpg" alt="" />
                </figure>
                <h3 class="location">Los Angeles</h3>
                <small class="date">8 oct, 8:00AM</small>
              </div>
            </div>
            <div class="col-md-3 col-sm-6">
              <div class="live-camera">
                <figure class="live-camera-cover">
                  <img src="@/assets/images/live-camera-3.jpg" alt="" />
                </figure>
                <h3 class="location">Chicago</h3>
                <small class="date">8 oct, 8:00AM</small>
              </div>
            </div>
            <div class="col-md-3 col-sm-6">
              <div class="live-camera">
                <figure class="live-camera-cover">
                  <img src="@/assets/images/live-camera-4.jpg" alt="" />
                </figure>
                <h3 class="location">London</h3>
                <small class="date">8 oct, 8:00AM</small>
              </div>
            </div>
          </div>
          <div class="row">
            <div class="col-md-3 col-sm-6">
              <div class="live-camera">
                <figure class="live-camera-cover">
                  <img src="@/assets/images/live-camera-5.jpg" alt="" />
                </figure>
                <h3 class="location">New York</h3>
                <small class="date">8 oct, 8:00AM</small>
              </div>
            </div>
            <div class="col-md-3 col-sm-6">
              <div class="live-camera">
                <figure class="live-camera-cover">
                  <img src="@/assets/images/live-camera-6.jpg" alt="" />
                </figure>
                <h3 class="location">Los Angeles</h3>
                <small class="date">8 oct, 8:00AM</small>
              </div>
            </div>
            <div class="col-md-3 col-sm-6">
              <div class="live-camera">
                <figure class="live-camera-cover">
                  <img src="@/assets/images/live-camera-7.jpg" alt="" />
                </figure>
                <h3 class="location">Chicago</h3>
                <small class="date">8 oct, 8:00AM</small>
              </div>
            </div>
            <div class="col-md-3 col-sm-6">
              <div class="live-camera">
                <figure class="live-camera-cover">
                  <img src="@/assets/images/live-camera-8.jpg" alt="" />
                </figure>
                <h3 class="location">London</h3>
                <small class="date">8 oct, 8:00AM</small>
              </div>
            </div>
          </div>
        </div>
      </div>
    </main>
    <!-- .main-content -->

    <TheFooter/>
    <!-- .site-footer -->
  </div>
</template>