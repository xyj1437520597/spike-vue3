<template>
  <div class="topnav">
    <div class="logo">
      <router-link to="/">

        <img style="width:30px; height: 30px" src="../logo.png" alt="">
      </router-link>
    </div>
    <ul class="menu">
      <li>
        <router-link to="/doc">文档</router-link>
      </li>
    </ul>
    <div v-if="toggleMenuButtonVisible" class="toggleAside">
      <svg aria-hidden="true" @click="toggleMenu">
        <use xlink:href="#icon-weibiaoti302"></use>
      </svg>
    </div>
  </div>
</template>

<script lang="ts">
import {
  inject,
  Ref
} from 'vue'

export default {
  props: {
    toggleMenuButtonVisible: {
      type: Boolean,
      default: false
    }
  },
  setup() {
    const menuVisible = inject<Ref<boolean>>('menuVisible') // get
    const toggleMenu = () => {
      menuVisible.value = !menuVisible.value
    }
    return {
      toggleMenu,
    }
  },
}
</script>

<style lang="scss" scoped>
.topnav {
  display: flex;
  padding: 16px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 10;
  justify-content: center;
  align-items: center;
  color: #36b1bf;
  box-shadow: 0 0 1px rgba(0, 0, 0, 0.25);

  >.logo {
    max-width: 6em;
    margin-right: auto;

    svg {
      width: 40px;
      height: 40px;
    }
  }

  >.menu {
    display: flex;
    white-space: nowrap;
    flex-wrap: nowrap;

    >li {
      margin: 0 1em;
    }
  }

  >.toggleAside {
    width: 24px;
    height: 24px;
    background-color: #fff;
    position: absolute;
    left: 16px;
    top: 50%;
    transform: translateY(-50%);
    display: none;
    box-shadow: 0 0 2px rgba(0, 0, 0, 0.25);

    >svg {
      color: #8f8f8f;
      position: absolute;
      width: 24px;
      height: 24px;
    }
  }

  @media (max-width: 500px) {
    padding: 0 !important;

    >.menu {
      display: none;
    }

    >.logo {
      margin: 0 auto;
    }

    >.toggleAside {
      display: inline-block;
    }
  }
}
</style>
