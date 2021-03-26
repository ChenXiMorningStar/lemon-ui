<template>
<div class="layout">
  <Topnav toggleMenuButtonVisible class="nav" />
  <div class="content">
    <transition name="myTransition">
      <aside v-show="menuVisible">
        <h2>文档</h2>
        <ol>
          <li>
            <router-link to="/doc/intro">介绍</router-link>
          </li>
          <li>
            <router-link to="/doc/install">安装</router-link>
          </li>
          <li>
            <router-link to="/doc/get-started">开始使用</router-link>
          </li>
        </ol>
        <h2>组件列表</h2>
        <ol>
          <li>
            <router-link to="/doc/switch">Switch 开关</router-link>
          </li>
          <li>
            <router-link to="/doc/button">Button 按钮</router-link>
          </li>
          <li>
            <router-link to="/doc/dialog">Dialog 对话框</router-link>
          </li>
          <li>
            <router-link to="/doc/tabs">Tabs 标签页</router-link>
          </li>
        </ol>
      </aside>
    </transition>
    <main>
      <router-view />
    </main>
  </div>
</div>
</template>

<script lang="ts">
import Topnav from "../components/Topnav.vue";
import {
  inject,
  Ref
} from "vue";
export default {
  components: {
    Topnav
  },
  setup() {
    const menuVisible = inject < Ref < boolean >> ("menuVisible"); // get
    return {
      menuVisible
    };
  },
};
</script>

<style lang="scss" scoped>
$aside-index : 10;

.layout {
  display: flex;
  flex-direction: column;
  height: 100vh;

  >.nav {
    flex-shrink: 0;
    background: #fff;
  }

  >.content {
    flex-grow: 1;
    padding-top: 60px;
    padding-left: 156px;

    @media (max-width: 500px) {
      padding-left: 0;
    }
  }
}

.content {
  display: flex;

  @media (max-width: 500px) {
    >aside {
      flex-shrink: 0;
    }
    >main {
      flex-grow: 1;
      padding: 16px;
      background: white;
      margin-top: 20px;
    }
  }
  @media (min-width: 800px) {
    >aside {
      flex-shrink: 0;
    }
    >main {
      flex-grow: 1;
      padding: 70px;
      background: white;
      margin-top: 20px;
      margin-left: 70px;
    }
  }
}

aside {
  width: 250px;
  @media (max-width: 500px) {
    width: 150px;
  }
  padding: 16px 0;
  position: fixed;
  top: 0;
  left: 0;
  padding-top: 70px;
  height: 100%;
  z-index: $aside-index;
  border-right: 1px solid #e8e8e8;
  box-shadow: 5px 0 5px rgb(51 51 51 / 10%);
  background: #fff;

  >h2 {
    margin: 15px 0 4px 0;
    padding: 0 16px;
    font-size: 120%;
    font-weight: 700;
  }

  >ol {
    >li {
      >a {
        display: block;
        padding: 0px 16px;
        text-decoration: none;
        height: 40px;
        line-height: 40px;
      }

      .router-link-active {
        background: linear-gradient(90deg, #fff -20%, rgb(173, 240, 210, 0.8) 70%);
      }
    }
  }
}

main {
  overflow: auto;
}

.myTransition-enter,
.myTransition-leave-to {
  transform: translateX(-250px);
}

.myTransition-enter-active,
.myTransition-leave-active {
  transition: all 0.8s ease;
}

.myTransition-enter-to,
.myTransition-leave {
  transform: translateX(0px);
}
</style>
