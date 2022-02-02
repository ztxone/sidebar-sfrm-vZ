<template>
  <div class="sidebar active">
    <div class="sidebar__logo-wrapper">
      <a class="sidebar__logo pointer" @click.prevent="redirectToMainPage">
        <div style="width:50px;height:40px;display:block;background:darkorange;margin:38px 0px;"></div>
      </a>
    </div>
    <hr class="sidebar__divider" />
    <!--<div class="btn-close-menu " @click="sidebarVisible=false"></div>-->
    <sidebar-menu />
  </div>
</template>

<script>
import SidebarMenu from "./nav/SidebarMenu.vue"

export default {
  components: {
    SidebarMenu
  },
  data () {
    return {
    }
  },
  methods: {
    redirectToMainPage () {
      this.$router.push('/')
    },
  }
}
</script>

<style lang="scss" scoped>
$cubic: cubic-bezier(0.4, 0.01, 0.165, 0.99);

.sidebar__logo-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  padding-top: 10px;
}
.logo-block-1 {
    fill: #ffbb61;
    transition: all 0.8s;
}

.logo-block-2 {
    fill: #d19752;
    transition: all 0.8s;
}
.logo-block-center {
    fill: #a67c52;
    transition: all 0.8s;
}
.logo-block-1:hover, .logo-block-2:hover, .logo-block-center:hover {
    fill: #ffd4a9;
    transition: all 0.1s;
}
.sidebar {
  user-select: none;
  position: relative;
  top: 0;
  left: 0;
  flex-shrink: 0;
  width: 232px;
  background-color: #191919;
  // border-right: 1px solid #242422;
  box-shadow: none;
  border-radius: 18px;

  &__divider {
    width: 100%;
    height: 1px;
    max-width: 180px;
    margin-top: 10px;
    margin-bottom: 10px;
    margin-left: auto;
    margin-right: auto;
    background-color: #242422;
    border: none;
  }
  
  &__logo svg {
    cursor: pointer;
    padding-top: 26px;
    padding-bottom: 16px;
    filter: drop-shadow(0px 0px 35px #DA9543);
  }
}

.btn-close-menu {
  display: none;
}
// @media (max-width: 868px) {
//   position: fixed;
//   left: -100%;
//   width: 100%;
//   height: auto;
//   padding-left: 20px;
//   transition: all 0.5s ease;
//   .btn-close-menu {
//     display: block;
//   }
// } 

</style>