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
            <li class="menu-item">
              <RouterLink :to="{ name: 'photos' }">Photos</RouterLink>
            </li>
            <li class="menu-item current-menu-item">
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
          <span>Contact</span>
        </div>
      </div>

      <div class="fullwidth-block">
        <div class="container">
          <div class="col-md-5">
            <div class="contact-details">
              <div class="map">
                <iframe
                  src="https://www.google.com/maps/embed?pb=!1m10!1m8!1m3!1d177203.33885891899!2d30.4926751085557!3d50.478290904289075!3m2!1i1024!2i768!4f13.1!5e0!3m2!1sru!2sua!4v1673902234584!5m2!1sru!2sua"
                  width="600"
                  height="450"
                  style="border: 0"
                  loading="lazy"
                  referrerpolicy="no-referrer-when-downgrade"
                ></iframe>
              </div>
              <div class="contact-info">
                <address>
                  <img src="@/assets/images/icon-marker.png" alt="" />
                  <p>
                    Company Name INC. <br />
                    2803 Avenue Street, Los Angeles
                  </p>
                </address>

                <a href="#"
                  ><img src="@/assets/images/icon-phone.png" alt="" />+1 800 314
                  235</a
                >
                <a href="#"
                  ><img
                    src="@/assets/images/icon-envelope.png"
                    alt=""
                  />contact@companyname.com</a
                >
              </div>
            </div>
          </div>
          <div class="col-md-6 col-md-offset-1">
            <h2 class="section-title">Contact us</h2>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Commodi
              consectetur inventore ducimus, facilis, numquam id soluta omnis
              eius recusandae nesciunt vero repellat harum cum. Nisi facilis
              odit hic, ipsum sed!
            </p>
            <form action="#" class="contact-form">
              <div class="row">
                <div class="col-md-6">
                  <input type="text" placeholder="Your name..." />
                </div>
                <div class="col-md-6">
                  <input type="text" placeholder="Email Addresss..." />
                </div>
              </div>
              <div class="row">
                <div class="col-md-6">
                  <input type="text" placeholder="Company name..." />
                </div>
                <div class="col-md-6">
                  <input type="text" placeholder="Website..." />
                </div>
              </div>
              <textarea name="" placeholder="Message..."></textarea>
              <div class="text-right">
                <input type="submit" placeholder="Send message" />
              </div>
            </form>
          </div>
        </div>
      </div>
    </main>
    <!-- .main-content -->

    <TheFooter/>
    <!-- .site-footer -->
  </div>
</template>