<template>
  <q-layout view="lHh Lpr lfr">
    <q-header>
      <q-bar class="bg-grey-9 default-toolbar">
        <q-toolbar-title> Title </q-toolbar-title>
        <q-btn class="toolbar-icon" flat icon="warning" />
        <q-btn class="toolbar-icon" flat icon="style" />
        <q-btn class="toolbar-icon" flat icon="print" />
        <q-btn flat no-caps>administrator</q-btn>
      </q-bar>
      <div class="bg-grey-4">
        <q-tabs
          indicator-color="grey-8"
          content-class="text-grey-8 bg-grey-4"
          active-class="text-grey-8 bg-white"
          no-caps
          align="left"
          dense
        >
          <q-route-tab class="grey-9" label="test1" to="/page1" />
          <q-route-tab class="grey-9" label="Contribution 1" to="/page2" />
          <q-route-tab class="grey-9" label="test3" to="/page3" />
        </q-tabs>
        <div class="indices bg-green">fixed-information</div>
      </div>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<style scoped lang="sass">
.indices
  width: 100%
  height: 150px

.default-toolbar
  height: 32px !important

.toolbar-icon
  width: 40px

.default-tab
  background-color: "grey-3"
  color: "grey-9"
</style>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "MainLayout",

  components: {},
  data() {
    return {
      leftDrawerOpen: true,
    };
  },
  methods: {},
});
</script>
