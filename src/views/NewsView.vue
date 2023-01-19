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
            <li class="menu-item current-menu-item">
              <RouterLink v-bind:to="{ name: 'news' }">News</RouterLink>
            </li>
            <li class="menu-item">
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
          <span>News</span>
        </div>
      </div>

      <div class="fullwidth-block">
        <div class="container">
          <div class="row">
            <div class="content col-md-8">
              <div class="post">
                <h2 class="entry-title">
                  Nemo enim ipsam voluptatem quia voluptas
                </h2>
                <div class="featured-image">
                  <img src="@/assets/images/featured-image-1.jpg" alt="" />
                </div>
                <p>
                  Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                  Dolorem nulla rem dolores unde et cum illum odio, enim quis
                  odit eveniet quaerat non libero, consequatur voluptatem harum
                  ad veritatis necessitatibus.
                </p>
                <a href="single.html" class="button">Read more</a>
              </div>

              <div class="post">
                <h2 class="entry-title">
                  Nemo enim ipsam voluptatem quia voluptas
                </h2>
                <div class="featured-image">
                  <img src="@/assets/images/featured-image-2.jpg" alt="" />
                </div>
                <p>
                  Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                  Dolorem nulla rem dolores unde et cum illum odio, enim quis
                  odit eveniet quaerat non libero, consequatur voluptatem harum
                  ad veritatis necessitatibus.
                </p>
                <a href="single.html" class="button">Read more</a>
              </div>

              <div class="post">
                <h2 class="entry-title">
                  Nemo enim ipsam voluptatem quia voluptas
                </h2>
                <div class="featured-image">
                  <img src="@/assets/images/featured-image-3.jpg" alt="" />
                </div>
                <p>
                  Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                  Dolorem nulla rem dolores unde et cum illum odio, enim quis
                  odit eveniet quaerat non libero, consequatur voluptatem harum
                  ad veritatis necessitatibus.
                </p>
                <a href="single.html" class="button">Read more</a>
              </div>
            </div>
            <div class="sidebar col-md-3 col-md-offset-1">
              <div class="widget">
                <h3 class="widget-title">Hot News</h3>
                <ul class="arrow-list">
                  <li><a href="#">Accusamus dignissimos</a></li>
                  <li><a href="#">Ducimus praesentium</a></li>
                  <li><a href="#">Voluptatum deleniti corrupti</a></li>
                  <li><a href="#">Wuos dolores excepturi sint</a></li>
                  <li><a href="#">Occaecati provident dolor</a></li>
                </ul>
              </div>

              <div class="widget">
                <h3 class="widget-title">Categories</h3>
                <ul class="arrow-list">
                  <li><a href="#">Nemo enim ipsam</a></li>
                  <li><a href="#">Voluptatem voluptas</a></li>
                  <li><a href="#">Aspernatur aut odit</a></li>
                  <li><a href="#">Consequuntur magni</a></li>
                  <li><a href="#">Dolores ratione</a></li>
                  <li><a href="#">Voluptatem nesciunt</a></li>
                  <li><a href="#">Neque porro quisquam</a></li>
                  <li><a href="#">Dolorem ipsum quia</a></li>
                </ul>
              </div>

              <div class="widget top-rated">
                <h3 class="widget-title">Top rated posts</h3>
                <ul>
                  <li>
                    <h3 class="entry-title">
                      <a href="#">Doloremque laudantium lorem</a>
                    </h3>
                    <div class="rating"><strong>5.5</strong> (759 rates)</div>
                  </li>
                  <li>
                    <h3 class="entry-title">
                      <a href="#">Doloremque laudantium lorem</a>
                    </h3>
                    <div class="rating"><strong>5.5</strong> (759 rates)</div>
                  </li>
                  <li>
                    <h3 class="entry-title">
                      <a href="#">Doloremque laudantium lorem</a>
                    </h3>
                    <div class="rating"><strong>5.5</strong> (759 rates)</div>
                  </li>
                  <li>
                    <h3 class="entry-title">
                      <a href="#">Doloremque laudantium lorem</a>
                    </h3>
                    <div class="rating"><strong>5.5</strong> (759 rates)</div>
                  </li>
                </ul>
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

<style>
</style>
