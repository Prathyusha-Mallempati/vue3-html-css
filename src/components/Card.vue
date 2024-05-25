<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="card-layout">
    <div class="data-card card" v-for="(item, index) in data" :key="index">
      <div class="container">
        <div>{{ item.name }}</div>
        <div><i :class="item.icon" class="icon"></i></div>
      </div>
      <h2 class="count">
        {{ item.count }}
      </h2>
      <div>
        <i class="mdi mdi-chart-line-variant stats-count"></i>
        <span class="stats-count">
          {{ item.countPercent }}
        </span>
        Since last week
      </div>
    </div>
  </div>
  <div class="card-layout">
    <div
      class="recent-card card"
      v-for="(item, index) in recentData"
      :key="index"
    >
      <h5>{{ item.name }}</h5>
      <div>
        <i class="mdi mdi-chart-line-variant stats-count"></i>
        <span class="stats-count">
          {{ item.percent }}
        </span>
      </div>
      <component :is="item.graph === 'bar' ? BarGraph : WaveGraph" style=" float: right;"> </component>
    </div>
  </div>
</template>
<script setup>
import BarGraph from "./BarGraph.vue";
import WaveGraph from "./WaveGraph.vue";
const data = [
  {
    name: "Document",
    icon: "mdi mdi-file-document",
    count: "146.000",
    countPercent: "17%",
  },
  {
    name: "Contact",
    icon: "mdi mdi-contacts",
    count: "1400",
    countPercent: "17%",
  },
  {
    name: "Email",
    icon: "mdi mdi-email",
    count: "150.700",
    countPercent: "17%",
  },
];

const recentData = [
  {
    name: "Recent Workflow",
    percent: "17%",
    graph: "wave",
  },
  {
    name: "Recent Marketing",
    percent: "17%",
    graph: "bar",
  },
];
</script>
<style scoped>
.container {
  display: flex;
  justify-content: space-between;
}
.card-layout {
  display: flex;
  gap: 20px;
  padding-bottom: 20px;
  width: inherit;
}
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  border-radius: 5px;
  padding: 20px;
  @media screen and (max-width: 1025px) {
    padding: 8px;
  }
}
.data-card {
  width: 270px;
  @media screen and (max-width: 1025px) {
    width: 180px
  }
  @media screen and (max-width: 769px) {
    width: 130px
  }
}
.recent-card {
  /* width: 390px; */
  width: 50%
}


.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}
.count {
  padding-top: 40px;
}
.icon {
  padding: 5px;
  background-color: #dfebf9;
  border-radius: 50%;
  color: #67c4da;
}
.stats-count {
  color: #7caa8f;
}
</style>
