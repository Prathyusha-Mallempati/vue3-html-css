<template>
  <div id="chart">
    <VueApexCharts
      type="bar"
      height="120"
      :options="chartOptions"
      :series="series"
    ></VueApexCharts>
  </div>
</template>

<script setup>
import VueApexCharts from "vue3-apexcharts";

const series = [
  {
    name: "Inflation",
    data: [2.3, 3.1, 4.0, 5.1, 7.8, 3.6, 3.2, 2.3, 1.4, 0.8, 0.5, 0.2],
  },
];
const chartOptions = {
  chart: {
    height: 300,
    type: "bar",
    stacked: true,
    toolbar: {
      show: false, // Hide the toolbar
    },
  },
  plotOptions: {
    bar: {
      horizontal: false, // Change to true if you want horizontal bars
      columnWidth: "40%",
    },
  },
  dataLabels: {
    enabled: false, // Hide the value labels on the bars
  },

  xaxis: {
    categories: [
      "Jan",
      "Feb",
      "Mar",
      "Apr",
      "May",
      "Jun",
      "Jul",
      "Aug",
      "Sep",
      "Oct",
      "Nov",
      "Dec",
    ],
    // position: "",
    axisBorder: {
      show: false,
    },
    axisTicks: {
      show: false,
    },
    crosshairs: {
      fill: {
        type: "gradient",
        gradient: {
          colorFrom: "#D8E3F0",
          colorTo: "#BED1E6",
          stops: [0, 100],
          opacityFrom: 0.4,
          opacityTo: 0.5,
        },
      },
    },
    tooltip: {
      enabled: true,
    },
  },
  yaxis: {
    axisBorder: {
      show: false,
    },
    axisTicks: {
      show: false,
    },
    labels: {
      show: false,
      formatter: function (val) {
        return val + "%";
      },
    },
  },
  grid: {
    show: false, // Remove horizontal grid lines
  },
};
</script>
<style></style>
