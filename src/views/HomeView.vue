<template>
  <div class="q-pa-md">
    <q-toolbar class="q-ma-sm">
      <q-input
        outlined
        v-model="text"
        label="Search"
        :dense="dense"
        rounded
        class="search"
      >
        <template v-slot:append>
          <q-icon name="search" />
        </template>
      </q-input>
      <q-space />
      <q-btn color="white" icon="fas fa-moon" text-color="black" />
    </q-toolbar>
    <q-toolbar>
      <h6 class="text-weight-bolder">Dashboard</h6>
      <q-space />
      <q-icon name="fas fa-calendar-minus" class="q-mr-sm" />
      <div class="text-overline">Wednesday, 21.03.2022</div>
    </q-toolbar>
    <div class="row q-col-gutter-md top">
      <div class="col-3">
        <q-card class="q-mx-md" bordered>
          <div class="flex flex-center column">
            <q-circular-progress
              show-value
              font-size="12px"
              value="70"
              size="100px"
              :thickness="0.22"
              color="green-7"
              track-color="green-2"
              class="q-ma-md"
            >
              78 Patients
            </q-circular-progress>
            <div>
              <q-badge color="green-2" rounded class="q-mr-sm">
                Woman 40%
              </q-badge>
            </div>
            <div class="q-mb-xl">
              <q-badge color="green-7" rounded class="q-mr-sm">
                Man 60%
              </q-badge>
            </div>
          </div>
        </q-card>
      </div>
      <div class="col-3">
        <q-card class="q-mx-md q-pa-md" bordered>
          <div class="text-overline">New patients</div>
          <div class="flex flex-center row">
            <div class="text-h4 text-weight-bolder q-mr-md">54</div>
            <q-chip
              color="green-1"
              text-color="green-3"
              icon="fas fa-chevron-up"
              >51%</q-chip
            >
          </div>
        </q-card>
        <q-card class="q-mx-md q-pa-md q-mt-sm" bordered>
          <div class="text-overline">Old patients</div>
          <div class="flex flex-center row">
            <div class="text-h4 text-weight-bolder q-mr-md">32</div>
            <q-chip color="red-1" text-color="red-3" icon="fas fa-chevron-down"
              >02%</q-chip
            >
          </div>
        </q-card>
      </div>
      <div class="col-6">
        <q-card class="q-mx-md q-pa-md doctor" bordered>
          <div class="text-overline">Statistic</div>
          <div>
            <q-carousel
              v-model="slide"
              vertical
              transition-prev="slide-down"
              transition-next="slide-up"
              swipeable
              animated
              control-color="green-7"
              navigation-icon="radio_button_unchecked"
              navigation
              padding
              arrows
              height="160px"
              class="text-black shadow-1 rounded-borders"
            >
              <q-carousel-slide name="style" class="column no-wrap flex-center">
                <q-icon name="style" size="36px" />
                <div class="q-mt-md text-center">{{ lorem }}</div>
              </q-carousel-slide>
              <q-carousel-slide name="tv" class="column no-wrap flex-center">
                <q-icon name="live_tv" size="36px" />
                <div class="q-mt-md text-center">{{ lorem }}</div>
              </q-carousel-slide>
              <q-carousel-slide name="layers" class="column no-wrap flex-center">
                <q-icon name="layers" size="36px" />
                <div class="q-mt-md text-center">{{ lorem }}</div>
              </q-carousel-slide>
            </q-carousel>
          </div>
        </q-card>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "HomeView",
  components: {},
  setup() {
    return {
      slide: ref("style"),
      lorem: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
      selection: ref(["green"]),
    };
  },
};
</script>
<style scoped>
.search {
  width: 700px;
}

.doctors {
  height: 200px;
}

.overlapping {
  border: 2px solid white;
  position: absolute;
  margin-left: -20px;
}

.card1 {
  height: 100px;
}

.top {
  margin-top: -40px;
}

.colorCard {
  background: #f8f8f8;
}
</style>
