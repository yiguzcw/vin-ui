<template>
  <div id="app" class="app">
    <!-- header -->
    <div class="header">vin-ui</div>
    <div class="main">
      <!-- sidebar -->
      <div class="sidebar">
        <!-- <router-link to="test">test</router-link> -->
        <nav-side :data="navsData"></nav-side>
      </div>
      <div class="view page-container">
        <router-view></router-view>
      </div>
      <div class="demos-container">
        <div class="demos">
          <section class="mofang-demo">
            <iframe
              :src="ifrSrc"
              frameborder="0"
              width="100%"
              height="100%"
              scrolling="no"
            ></iframe>
          </section>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import navSide from "./components/nav-side";
import navsData from "./nav.config.json";
export default {
  components: {
    navSide
  },
  data() {
    return {
      ifrSrc: "",
      navsData
    };
  }
};
</script>
<style lang="less">
html,
body {
  margin: 0;
  height: 100%;
}
.app {
  width: 100%;
  height: 100%;
  position: relative;
  box-sizing: border-box;
  padding: 60px 0 20px;
  .header {
    position: absolute;
    width: 100%;
    height: 60px;
    top: 0;
    background-color: antiquewhite;
  }
  .main {
    height: 100%;
    width: 100%;
    display: flex;
    flex-direction: row;
    overflow: hidden;
    .sidebar,
    .view {
      height: 100%;
      overflow-y: scroll;
    }
    .demos {
      height: 100%;
    }
  }
}

.sidebar {
  width: 250px;
  padding-left: 20px;
  flex-shrink: 0;
}
.view {
  min-width: 250px;
  flex-grow: 5;
}
.demos-container {
  width: 330px;
  flex-shrink: 0;
  .demos {
    width: 330px;
    position: absolute;
    top: 50%;
    transform: translate(0, -50%);
    margin: 0 5px;
    background: url("./assets/iphoneX.png") no-repeat center 0;
    background-size: 100%;
  }

  .mofang-demo {
    position: absolute;
    top: 64px;
    left: 21px;
    right: 23px;
    bottom: 22px;
    overflow: hidden;
    border-radius: 0 0 35px 35px;
    border: 1px solid #edf0f4;
    border-top: none;
    background-color: #edf0f4;
    iframe {
      // safari shit
      width: 0;
      max-width: 100%;
      min-width: 100%;
    }
  }
}
</style>
