<template>
  <div id="app">
    <el-container>
      <el-header>
        <img
          class="logo"
          src="./assets/logo.png"
        > MY GOPHER
      </el-header>
      <el-main>
        <svg
          width="300px"
          viewBox="0 0 1832 2495"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink">
          <g id="gopher">
            <Foot></Foot>
            <Hand></Hand>
            <GBody
              :color="body_color"
              :lineColor="body_line_color"
            ></GBody>
            <Tooth></Tooth>
            <Eye></Eye>
            <Nose></Nose>
          </g>
        </svg>
        <div class="parts">
          <el-tabs
            type="card"
            tab-position="bottom"
          >
            <el-tab-pane>
              <span slot="label"><img src="./assets/body.svg"></span>
              <el-color-picker
                v-model="body_color"
                @active-change="changeColor5"
                size="mini"
              ></el-color-picker>
            </el-tab-pane>
            <el-tab-pane>
              <span slot="label"><img src="./assets/body-line.svg"></span>
              <el-color-picker
                v-model="body_line_color"
                @active-change="changeColor6"
                size="mini"
              ></el-color-picker>
            </el-tab-pane>
            <el-tab-pane>
              <span slot="label"><img src="./assets/hand1.svg"></span>
              <el-color-picker
                v-model="hand1_color"
                @active-change="changeColor1"
                size="mini"
              ></el-color-picker>
            </el-tab-pane>
            <el-tab-pane>
              <span slot="label"><img src="./assets/hand2.svg"></span>
              <el-color-picker
                v-model="hand2_color"
                @active-change="changeColor2"
                size="mini"
              ></el-color-picker>
            </el-tab-pane>
            <el-tab-pane>
              <span slot="label"><img src="./assets/foot1.svg"></span>
              <el-color-picker
                v-model="foot1_color"
                @active-change="changeColor3"
                size="mini"
              ></el-color-picker>
            </el-tab-pane>
            <el-tab-pane>
              <span slot="label"><img src="./assets/foot2.svg"></span>
              <el-color-picker
                v-model="foot2_color"
                @active-change="changeColor4"
                size="mini"
              ></el-color-picker>
            </el-tab-pane>
            <el-tab-pane>
              <span slot="label"><img src="./assets/eye1.svg"></span>
              <el-color-picker
                v-model="eye1_color"
                @active-change="changeColor7"
                size="mini"
              ></el-color-picker>
            </el-tab-pane>
            <el-tab-pane>
              <span slot="label"><img src="./assets/eye2.svg"></span>
              <el-color-picker
                v-model="eye2_color"
                @active-change="changeColor8"
                size="mini"
              ></el-color-picker>
            </el-tab-pane>
          </el-tabs>
        </div>
      </el-main>
    </el-container>
  </div>
</template>
<script>
import Body from "./components/Body.vue";
import Foot from "./components/Foot.vue";
import Hand from "./components/Hand.vue";
import Tooth from "./components/Tooth.vue";
import Eye from "./components/Eye.vue";
import Nose from "./components/Nose.vue";
export default {
  name: "app",
  data() {
    return {
      body_color: "#69D7E2",
      body_line_color: "#000000",
      hand1_color: "#F6D2A2",
      hand2_color: "#F6D2A2",
      foot1_color: "#F6D2A2",
      foot2_color: "#F6D2A2",
      eye1_color: "#FFFFFF",
      eye2_color: "#FFFFFF"
    };
  },
  components: {
    GBody: Body,
    Foot: Foot,
    Hand: Hand,
    Tooth: Tooth,
    Eye: Eye,
    Nose: Nose
  },
  methods: {
    changeColor1: function(color) {
      this.hand1_color = color;
    },
    changeColor2: function(color) {
      this.hand2_color = color;
    },
    changeColor3: function(color) {
      this.foot1_color = color;
    },
    changeColor4: function(color) {
      this.foot2_color = color;
    },
    changeColor5: function(color) {
      this.body_color = color;
    },
    changeColor6: function(color) {
      this.body_line_color = color;
    },
    changeColor7: function(color) {
      this.eye1_color = color;
    },
    changeColor8: function(color) {
      this.eye2_color = color;
    }
  }
};
</script>

<style>
body {
  margin: 0;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.el-header {
  line-height: 60px;
}

.el-header .logo {
  height: 30px;
  vertical-align: middle;
}

.el-main {
  text-align: center;
}

.parts {
  margin-top: 60px;
}

.parts img {
  height: 28px;
  width: 28px;
  vertical-align: middle;
}
</style>