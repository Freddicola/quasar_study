<template>
  <q-page padding ref="page" :style-fn="make_layout">
    <div>
      <div class="row" :style="content_height" ref="row1">
        <div class="col-6 bg-red-4">a</div>
        <div class="col-6 bg-blue-4">b</div>
      </div>
      <div class="row" :style="content_height" ref="row2">
        <div class="col-5 bg-grey-8">c</div>
        <div class="col-7 bg-yellow-3" ref="plane">d</div>
      </div>
    </div>
  </q-page>
</template>

<style lang="sass">
.content
  height: 100% !important

.content div
  height: 50% !important
</style>

<script>
import Plotly from "plotly.js-dist-min";

export default {
  name: "Page1",
  data() {
    return {
      size: 0,
      content_height: "height: 100px;",
    };
  },
  methods: {
    make_layout: function (offset, height) {
      const content_height = (height - offset - 50) * 0.5;
      console.log("content_height:", content_height);
      this.content_height = `height: ${content_height}px;`;
    },
  },
  computed: {},
  mounted: function () {
    const plane = this.$refs.plane;
    const x = [
      "2020-02",
      "2020-03",
      "2020-04",
      "2020-05",
      "2020-06",
      "2020-07",
      "2020-08",
    ];
    const y = [10.3, 15.2, 15.9, 10.2, 11.3, null, 12.3];

    const series = {
      x: x,
      y: y,
      mode: "lines+markers",
      connectgaps: true,
    };

    const threshold = {
      x: ["2020-01", "2020-09"],
      y: [9.0, 9.0],
      mode: "lines",
      connectgaps: true,
    };

    const layout = {
      xaxis: {
        type: "date",
      },
      yaxis: {
        range: [0.0, 16.0],
        dtick: 3.0,
      },
    };

    Plotly.newPlot(plane, [series, threshold], layout);
  },
};
</script>
