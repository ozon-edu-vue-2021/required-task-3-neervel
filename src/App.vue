<template>
  <div id="app">
    <div class="office">
      <Map 
        @select-table="showInfo"
        @click-out="hideInfo"
      />
      <SideMenu
        :person="tableInfo"
        :isUserOpened="isInfoShow"
        @update:isUserOpened="hideInfo"
      />
    </div>
  </div>
</template>

<script>
import Map from "./components/Map.vue";
import SideMenu from "./components/SideMenu.vue";

export default {
  name: "App",
  components: {
    Map,
    SideMenu,
  },
  data() {
    return {
      isInfoShow: false,
      tableInfo: {}
    }
  },
  methods: {
    showInfo(tableInfo) {
      this.tableInfo = tableInfo
      this.isInfoShow = true
    },
    hideInfo() {
      this.isInfoShow = false
    }
  }
};
</script>

<style>
#app {
  font-family: 'Raleway', sans-serif;
  color: #2c3e50;
  background-color: #fafafa;
  padding: 24px;
  box-sizing: border-box;
}

html,
body,
#app {
  height: 100%;
}

* {
  box-sizing: border-box;
}

h3 {
  margin-top: 0px;
}

.office {
  display: grid;
  grid-template-columns: 1fr 450px;
  border-radius: 6px;
  border: 1px solid #ccd8e4;
  height: 100%;
  background: white;
  max-width: 1500px;
  margin: 0 auto;
}
</style>
