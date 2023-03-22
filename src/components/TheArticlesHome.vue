<script setup>
defineProps({
  articles: {
    required: true
  },
})
</script>

<template>
      <div class="fullwidth-block" data-bg-color="#262936">
        <div class="container">
          <div class="row">
            <div  v-for="item of articles" :key="item.id" class="col-md-4">
              <div class="news">
                <div class="date">{{ item.postTime }}</div>
                <h3><a href="#">{{ item.title }}</a></h3>
                <p>
                  {{ item.text }}
                </p>
              </div>
            </div>
          </div>
        </div>
      </div> 
</template>

<style scoped>
.fullwidth-block {
  background-color: #262936;
}
</style>