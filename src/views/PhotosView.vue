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
            <li class="menu-item">
              <RouterLink :to="{ name: 'live-cameras' }"
                >Live cameras</RouterLink
              >
            </li>
            <li class="menu-item current-menu-item">
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
          <span>Photos</span>
        </div>
      </div>
      <div class="fullwidth-block">
        <div class="container">
          <div class="row">
            <div class="col-md-6">
              <div class="photo">
                <div class="photo-preview photo-detail" id="photo-1"></div>
                <div class="photo-details">
                  <h3 class="photo-title">
                    <a href="#">Neque porro quisquam</a>
                  </h3>
                  <p>
                    Atatem accusantium aperiam eaque quae quasi architecto
                    beatae vitae dicta sunt explicabo nemo enim.
                  </p>
                  <div class="star-rating" title="Rated 1 out of 5">
                    <span style="width: 60%"
                      ><strong class="rating">1</strong> out of 5</span
                    >
                  </div>
                </div>
              </div>
              <div class="photo">
                <div class="photo-preview photo-detail" id="photo-2"></div>
                <div class="photo-details">
                  <h3 class="photo-title">
                    <a href="#">Neque porro quisquam</a>
                  </h3>
                  <p>
                    Atatem accusantium aperiam eaque quae quasi architecto
                    beatae vitae dicta sunt explicabo nemo enim.
                  </p>
                  <div class="star-rating" title="Rated 1 out of 5">
                    <span style="width: 60%"
                      ><strong class="rating">1</strong> out of 5</span
                    >
                  </div>
                </div>
              </div>
              <div class="photo">
                <div class="photo-preview photo-detail" id="photo-3"></div>
                <div class="photo-details">
                  <h3 class="photo-title">
                    <a href="#">Neque porro quisquam</a>
                  </h3>
                  <p>
                    Atatem accusantium aperiam eaque quae quasi architecto
                    beatae vitae dicta sunt explicabo nemo enim.
                  </p>
                  <div class="star-rating" title="Rated 1 out of 5">
                    <span style="width: 60%"
                      ><strong class="rating">1</strong> out of 5</span
                    >
                  </div>
                </div>
              </div>
              <div class="photo">
                <div class="photo-preview photo-detail" id="photo-4"></div>
                <div class="photo-details">
                  <h3 class="photo-title">
                    <a href="#">Neque porro quisquam</a>
                  </h3>
                  <p>
                    Atatem accusantium aperiam eaque quae quasi architecto
                    beatae vitae dicta sunt explicabo nemo enim.
                  </p>
                  <div class="star-rating" title="Rated 1 out of 5">
                    <span style="width: 60%"
                      ><strong class="rating">1</strong> out of 5</span
                    >
                  </div>
                </div>
              </div>
              <div class="photo">
                <div class="photo-preview photo-detail" id="photo-5"></div>
                <div class="photo-details">
                  <h3 class="photo-title">
                    <a href="#">Neque porro quisquam</a>
                  </h3>
                  <p>
                    Atatem accusantium aperiam eaque quae quasi architecto
                    beatae vitae dicta sunt explicabo nemo enim.
                  </p>
                  <div class="star-rating" title="Rated 1 out of 5">
                    <span style="width: 60%"
                      ><strong class="rating">1</strong> out of 5</span
                    >
                  </div>
                </div>
              </div>
            </div>
            <div class="col-md-6">
              <div class="photo">
                <div class="photo-preview photo-detail" id="photo-6"></div>
                <div class="photo-details">
                  <h3 class="photo-title">
                    <a href="#">Neque porro quisquam</a>
                  </h3>
                  <p>
                    Atatem accusantium aperiam eaque quae quasi architecto
                    beatae vitae dicta sunt explicabo nemo enim.
                  </p>
                  <div class="star-rating" title="Rated 1 out of 5">
                    <span style="width: 60%"
                      ><strong class="rating">1</strong> out of 5</span
                    >
                  </div>
                </div>
              </div>
              <div class="photo">
                <div class="photo-preview photo-detail" id="photo-7"></div>
                <div class="photo-details">
                  <h3 class="photo-title">
                    <a href="#">Neque porro quisquam</a>
                  </h3>
                  <p>
                    Atatem accusantium aperiam eaque quae quasi architecto
                    beatae vitae dicta sunt explicabo nemo enim.
                  </p>
                  <div class="star-rating" title="Rated 1 out of 5">
                    <span style="width: 60%"
                      ><strong class="rating">1</strong> out of 5</span
                    >
                  </div>
                </div>
              </div>
              <div class="photo">
                <div class="photo-preview photo-detail" id="photo-8"></div>
                <div class="photo-details">
                  <h3 class="photo-title">
                    <a href="#">Neque porro quisquam</a>
                  </h3>
                  <p>
                    Atatem accusantium aperiam eaque quae quasi architecto
                    beatae vitae dicta sunt explicabo nemo enim.
                  </p>
                  <div class="star-rating" title="Rated 1 out of 5">
                    <span style="width: 60%"
                      ><strong class="rating">1</strong> out of 5</span
                    >
                  </div>
                </div>
              </div>
              <div class="photo">
                <div class="photo-preview photo-detail" id="photo-9"></div>
                <div class="photo-details">
                  <h3 class="photo-title">
                    <a href="#">Neque porro quisquam</a>
                  </h3>
                  <p>
                    Atatem accusantium aperiam eaque quae quasi architecto
                    beatae vitae dicta sunt explicabo nemo enim.
                  </p>
                  <div class="star-rating" title="Rated 1 out of 5">
                    <span style="width: 60%"
                      ><strong class="rating">1</strong> out of 5</span
                    >
                  </div>
                </div>
              </div>
              <div class="photo">
                <div class="photo-preview photo-detail" id="photo-10"></div>
                <div class="photo-details">
                  <h3 class="photo-title">
                    <a href="#">Neque porro quisquam</a>
                  </h3>
                  <p>
                    Atatem accusantium aperiam eaque quae quasi architecto
                    beatae vitae dicta sunt explicabo nemo enim.
                  </p>
                  <div class="star-rating" title="Rated 1 out of 5">
                    <span style="width: 60%"
                      ><strong class="rating">1</strong> out of 5</span
                    >
                  </div>
                </div>
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

<style scoped>
#photo-1 {
  background-image: url("@/assets/images/photo-1.jpg");
}
#photo-2 {
  background-image: url("@/assets/images/photo-2.jpg");
}
#photo-3 {
  background-image: url("@/assets/images/photo-3.jpg");
}
#photo-4 {
  background-image: url("@/assets/images/photo-4.jpg");
}
#photo-5 {
  background-image: url("@/assets/images/photo-5.jpg");
}
#photo-6 {
  background-image: url("@/assets/images/photo-9.jpg");
}
#photo-7 {
  background-image: url("@/assets/images/photo-7.jpg");
}
#photo-8 {
  background-image: url("@/assets/images/photo-8.jpg");
}
#photo-9 {
  background-image: url("@/assets/images/photo-9.jpg");
}
#photo-10 {
  background-image: url("@/assets/images/photo-10.jpg");
}
</style>