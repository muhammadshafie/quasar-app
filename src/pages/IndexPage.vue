<template>
  <q-layout view="hHh lpR fFf">
    <q-header
      elevated
      class="q-py-md text-white"
      style="background-color: #fff"
    >
      <q-toolbar>
        <q-toolbar-title class="">
          <img
            class="q-pl-lg img-fluid justify-center items-center content-center"
            src="../assets/logo.png"
          />
        </q-toolbar-title>
        <q-tabs align="left" class="gt-sm">
          <q-route-tab class="home-button" to="/page1" label="Home" />
          <q-route-tab class="home-button" to="/page2" label="About Us" />
          <q-route-tab class="home-button" to="/page3" label="Our Programmes" />
          <q-route-tab class="home-button" to="/page3" label="Newsroom" />
          <q-route-tab class="home-button" to="/page3" label="Our Partners" />
        </q-tabs>

        <q-btn
          to="/page2"
          unelevated
          rounded
          style="background: #f37435; color: white; margin: 10px"
          label="Get Involved"
        />
        <div class="lt-md">
          <q-btn
            dense
            flat
            round
            color="black"
            icon="menu"
            @click="toggleRightDrawer"
          />
        </div>
      </q-toolbar>
    </q-header>
    <q-drawer v-model="rightDrawerOpen" side="right" bordered>
      <q-list>
        <q-item-label header>Essential Links </q-item-label>
        <!-- <q-item clickable tag="a" target="_blank" :href="link">
          <q-item-section>
            <q-item-label>Test</q-item-label>
            <q-item-label caption>Test2</q-item-label>
          </q-item-section>
        </q-item> -->
        <q-btn-dropdown label="Dropdown Button">
          <q-list>
            <q-item clickable v-close-popup @click="onItemClick">
              <q-item-section>
                <q-item-label>Photos</q-item-label>
              </q-item-section>
            </q-item>

            <q-item clickable v-close-popup @click="onItemClick">
              <q-item-section>
                <q-item-label>Videos</q-item-label>
              </q-item-section>
            </q-item>

            <q-item clickable v-close-popup @click="onItemClick">
              <q-item-section>
                <q-item-label>Articles</q-item-label>
              </q-item-section>
            </q-item>
          </q-list>
        </q-btn-dropdown>
      </q-list>
    </q-drawer>
    <q-carousel
      class="q-pa-none"
      animated
      v-model="slide"
      arrows
      navigation
      infinite
      control-color="orange"
      height="100vh"
    >
      <q-carousel-slide
        class="carousel-item"
        :name="1"
        img-src="https://cdn.quasar.dev/img/mountains.jpg"
      >
        <div class="absolute-bottom carousel-caption">
          <div class="text-subtitle1">Mountains</div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide
        class="carousel-item"
        :name="2"
        img-src="https://cdn.quasar.dev/img/parallax1.jpg"
      >
        <div
          class="absolute-bottom justify-center items-center content-center carousel-caption"
        >
          <div class="text-subtitle1">Mountains</div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide
        class="carousel-item"
        :name="3"
        img-src="https://cdn.quasar.dev/img/parallax2.jpg"
      >
        <div class="absolute-bottom carousel-caption">
          <div class="text-subtitle1">Mountains</div>
        </div>
      </q-carousel-slide>
    </q-carousel>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "IndexPage",

  setup() {
    const rightDrawerOpen = ref(false);

    return {
      slide: ref(1),
      rightDrawerOpen,
      toggleRightDrawer() {
        rightDrawerOpen.value = !rightDrawerOpen.value;
      },
    };
  },
});
</script>

<style scoped>
.img-fluid {
  max-width: 150px;
  height: auto;
}

.home-button {
  color: #000;
}
.home-button:hover {
  color: #f37435;
}

.carousel-caption {
  opacity: 0;
  text-align: center;
  padding: 18px;
  color: #000;
  -webkit-transition: all 0.4s;
  transition: all 0.4s;
  transition: all ease-in-out 0.3s;
  background: rgba(255, 255, 255, 0.9);
  padding: 15px;
  bottom: 10%;
}

.carousel-item:hover .carousel-caption {
  opacity: 1;
}
</style>
