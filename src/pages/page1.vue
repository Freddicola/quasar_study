<template>
  <q-page padding ref="page" :style-fn="make_layout">
    <div>
      <div class="row" :style="content_height" ref="row1">
        <div class="col-6 bg-red-4">a</div>
        <div class="col-6 bg-blue-4">b</div>
      </div>
      <div class="row" :style="content_height" ref="row2">
        <div class="col-5 bg-grey-8">c</div>
        <div class="col-7 bg-yellow-3">d</div>
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
  mounted: function () {},
};
</script>
