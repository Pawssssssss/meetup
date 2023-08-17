<template>
  <v-container>
    <v-layout class="btn-container d-flex flex-wrap align-start justify-center">
      <div class="d-flex align-start justify-center">
        <v-btn large router to="/event">Explore Events</v-btn>
      </div>
      <div class="d-flex align-start justify-start ">
        <v-btn large router to="/event/new">Organize Events</v-btn>
      </div>
    </v-layout>
  </v-container>

  <v-layout class="d-flex flex-wrap align-start justify-center">
    <v-carousel show-arrows="hover">
      <v-carousel-item v-for="event in events" :src="event.imgUrl" :key="event.id">
        <div class="carousel-content">
          <img :src="event.imgUrl" alt="Event Image" class="carousel-image" />
          <div class="title">{{ event.title }}</div>
        </div>
      </v-carousel-item>
    </v-carousel>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {
      events: [
        { imgUrl: 'https://img.salehere.co.th/p/1200x0/2022/01/20/swprgz8zwcl4.jpg', id: 'suan100', title: 'สวนร้อยปี' },
        { imgUrl: 'https://coconuts.co/wp-content/uploads/2019/08/DSC09487.jpg', id: 'lidoconnect', title: 'ลิโด้สยาม' }
      ]
    };
  }
}
</script>


<style scoped>
.btn-container {
  margin-top: 20px;
}

/* .carousel-content {
  position: relative;
  text-align: center;
  justify-content: center;
}  */

.carousel-image {
  width: 100%;
  height: auto;
}

.title {
  position: absolute;
  text-align: center;
  margin-left: 0;
  bottom: 50px;
  left: 583px;
  padding: 20px;
  background-color: rgba(0, 0, 0, 0.7);
  color: white;
}
</style>

1268.8
103/2 = 51.5