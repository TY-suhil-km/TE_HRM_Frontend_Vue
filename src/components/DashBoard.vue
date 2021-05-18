<template>
  <div class="main">
    <div class="card">
      <div class="card-body row">
        <div class="col-1 pr-4 pl-4 pt-3 text-end">
          <i class="fas fa-tachometer-alt"></i>
        </div>
        <div class="col-4 d-flex flex-column pl-0">
          <span class="h7">Dashboard</span>
          <span class="h3">HR DashBoard</span>
          <span class="h6"
            >Lorem ipsum dolor sit amet consectetur adipisicing elit.</span
          >
        </div>
        <div class="col-5"></div>
        <div class="col-2">
          <div
            class="btn-group"
            role="group"
            aria-label="Basic outlined example"
          >
            <button type="button" class="btn btn-outline-primary text-primary">
              Refresh
            </button>
            <button type="button" class="btn btn-outline-primary text-primary">
              Edit
            </button>
            <button type="button" class="btn btn-outline-primary text-primary">
              <i class="fas fa-sort-down"></i>
            </button>
          </div>
        </div>
      </div>
    </div>
    <div class="main-container row">
      <div class="card col-4">
        <div class="card-body shadow-sm">
          <VueApexCharts
            width="500"
            type="bar"
            :options="options"
            :series="series"
          ></VueApexCharts>
        </div>
      </div>
      <div class="card col-4">
        <div class="card-body shadow-sm">
          <VueApexCharts
            type="bar"
            height="350"
            :options="chartOptions"
            :series="columnSeries"
          ></VueApexCharts>
        </div>
      </div>
      <div class="card col-4">
        <div class="card-body shadow-sm">
          <VueApexCharts
            width="500"
            type="donut"
            :options="donutOptions"
            :series="donutSeries"
          ></VueApexCharts>
        </div>
      </div>
      <div class="card col-4">
        <div class="card-body shadow-sm">
          <VueApexCharts
            type="bar"
            height="380"
            :options="horizontalChartOptions"
            :series="horizontalSeries"
          ></VueApexCharts>
        </div>
      </div>
      <div class="card col-4">
        <div class="card-body shadow-sm">
          <VueApexCharts
            width="500"
            type="donut"
            :options="donutOptions"
            :series="donutSeries"
          ></VueApexCharts>
        </div>
      </div>
      <div class="card col-4">
        <div class="card-body shadow-sm">
          <VueApexCharts
            width="500"
            type="donut"
            :options="donutOptions"
            :series="donutSeries"
          ></VueApexCharts>
        </div>
      </div>
      <div class="card col-6">
        <div class="card-body shadow-sm">
          <VueApexCharts
            width="500"
            type="donut"
            :options="donutOptions"
            :series="donutSeries"
          ></VueApexCharts>
        </div>
      </div>
      <div class="card col-6">
        <div class="card-body shadow-sm">
          <VueApexCharts
            type="bar"
            height="380"
            :options="horizontalChartOptions"
            :series="horizontalSeries"
          ></VueApexCharts>
        </div>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import VueApexCharts from "vue-apexcharts";

@Component({
  components: {
    VueApexCharts,
  },
})
export default class DashBoard extends Vue {
  //bar chart
  options = {
    chart: {
      id: "vuechart-example",
    },
    xaxis: {
      categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998],
    },
  };
  series = [
    {
      name: "series-1",
      data: [30, 40, 45, 50, 49, 60, 70, 91],
    },
  ];

  //donut chart
  donutOptions = {};
  donutSeries = [44, 55, 41, 17, 15];

  //column gragh
  columnSeries = [
    {
      name: "PRODUCT A",
      data: [44, 55, 41, 67, 22, 43],
    },
    {
      name: "PRODUCT B",
      data: [13, 23, 20, 8, 13, 27],
    },
    {
      name: "PRODUCT C",
      data: [11, 17, 15, 15, 21, 14],
    },
    {
      name: "PRODUCT D",
      data: [21, 7, 25, 13, 22, 8],
    },
  ];
  chartOptions = {
    chart: {
      type: "bar",
      height: 350,
      stacked: true,
      toolbar: {
        show: true,
      },
      zoom: {
        enabled: true,
      },
    },
    responsive: [
      {
        breakpoint: 480,
        options: {
          legend: {
            position: "bottom",
            offsetX: -10,
            offsetY: 0,
          },
        },
      },
    ],
    plotOptions: {
      bar: {
        borderRadius: 8,
        horizontal: false,
      },
    },
    xaxis: {
      type: "datetime",
      categories: [
        "01/01/2011 GMT",
        "01/02/2011 GMT",
        "01/03/2011 GMT",
        "01/04/2011 GMT",
        "01/05/2011 GMT",
        "01/06/2011 GMT",
      ],
    },
    legend: {
      position: "right",
      offsetY: 40,
    },
    fill: {
      opacity: 1,
    },
  };

  //horizontal bar graph
  horizontalSeries = [
    {
      data: [400, 430, 448, 470, 540, 580, 690, 1100, 1200, 1380],
    },
  ];

  horizontalChartOptions = {
    chart: {
      type: "bar",
      height: 380,
    },
    plotOptions: {
      bar: {
        barHeight: "100%",
        distributed: true,
        horizontal: true,
        dataLabels: {
          position: "bottom",
        },
      },
    },
    colors: [
      "#33b2df",
      "#546E7A",
      "#d4526e",
      "#13d8aa",
      "#A5978B",
      "#2b908f",
      "#f9a3a4",
      "#90ee7e",
      "#f48024",
      "#69d2e7",
    ],
  };
}
</script>

<style scoped>
.fa-tachometer-alt {
  font-size: 40px;
}
.card {
  background-color: #ededed;
}
.btn {
  font-weight: bold;
}
.main-container {
  padding: 10px 15px;
  margin-top: 10px;
}
.main {
  background-color: #f7f3f3;
  width: 100vw;
  height: 100vh;
}
.main-container > .card {
  background-color: #f7f3f3;
  border: none;
  border-radius: 0.25rem;
  padding: 8px;
}
.main-container > .card > .card-body {
  border: 1px solid rgba(0, 0, 0, 0.125);
  border-radius: 0.25rem;
  background-color: white;
}
</style>
<style>
::-webkit-scrollbar {
  display: none;
}
</style>