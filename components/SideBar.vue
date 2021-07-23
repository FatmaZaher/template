<template>
  <div>
    <div
      class="overlay"
      v-bind:class="{ opcity1: withOverlay, opcity0: noOverlay }"
      @click="hidesidebar"
    ></div>
    <sidebar-menu
      :menu="SideBarMenu"
      width="270px"
      widthCollapsed="50px"
      theme="white-theme"
      v-bind:class="{ ShowSideBar: show, HideSideBar: hide }"
    >
      <div slot="header">
        <span class="showSideBar" @click="showsidebar">»</span>
        <div class="user-card d-flex w-100 justify-content-center py-4">
          <div class="image">
            <img src="~/assets/images/Photo.png" alt="Person image" />
          </div>
          <div class="text text-left ml-3 d-flex align-items-center">
            <div>
              <h6 class="mb-3">اسم الشخص</h6>
              <p>اسم التخصص</p>
          </div>
          </div>
        </div>
      </div>
      <span slot="dropdown-icon"
        ><svg
          xmlns="http://www.w3.org/2000/svg"
          width="20"
          height="22"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="feather feather-chevron-left"
        >
          <polyline points="15 18 9 12 15 6"></polyline></svg
      ></span>
    </sidebar-menu>
  </div>
</template>

<script>
import { SidebarMenu } from 'vue-sidebar-menu'
import 'vue-sidebar-menu/dist/vue-sidebar-menu.css'
import SideBarItems from './SideBar.json'

export default {
  components: {
    SidebarMenu,
  },
  data() {
    return {
      SideBarMenu: [],
      show: false,
      hide: true,
      noOverlay: true,
      withOverlay: false,
    }
  },
  mounted() {
    this.SideBarMenu = SideBarItems
  },
  methods: {
    showsidebar() {
      if (this.hide) {
        this.show = true
        this.hide = false
        this.withOverlay = true
        this.noOverlay = false
      } else {
        this.show = false
        this.hide = true
        this.withOverlay = false
        this.noOverlay = true
      }
    },
    hidesidebar() {
      this.show = false
      this.hide = true
      this.withOverlay = false
      this.noOverlay = true
    },
  },
}
</script>
<style lang="scss">
.overlay {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  z-index: 4;
  left: 0;
  background-color: #00000087;
  transition: 0.5s ease;
  opacity: 0;
  display: none;
}
.v-sidebar-menu {
  left: 30px;
  text-align: left;
  top: 30px;
  bottom: 30px;
  padding: 0 10px;
  border-radius: 20px;
  box-shadow: 0 3px 36px 0 rgb(0 0 0 / 10%);
  margin-right: 35px;
  transition: left 0.5s ease;
  @media (max-width: 767px) {
    border-radius: 0 20px 20px 0;
  }
  .user-card {
    .image img {
      width: 80px;
      height: 80px;
    }
    .text h6 {
      color: var(--text-color);
    }
    .text p {
      color: var(--muted-color);
      font-size: 14px;
      margin-bottom: 0;
    }
  }
  .vsm--link {
    font-size: 14px;
    padding: 5px;
    padding-left: 10px;
    margin: 5px;
    border-radius: 25px;
  }
  .vsm--toggle-btn {
    display: none;
  }
  .showSideBar {
    color: #ffffff;
    position: absolute;
    right: -29px;
    top: 95px;
    width: 30px;
    height: 30px;
    font-size: 20px;
    line-height: 30px;
    text-align: center;
    border-radius: 0 25px 25px 0;
    box-shadow: 0 3px 36px 0 rgb(0 0 0 / 10%);
    background-color: var(--main-color);
    transition: 0.5s ease;
    opacity: 0;
    @media (max-width: 767px) {
      opacity: 1;
      cursor: pointer;
    }
  }
}
.v-sidebar-menu.vsm_white-theme .vsm--link {
  color: var(--text-color);
}
.v-sidebar-menu.vsm_white-theme .vsm--link_level-1 .vsm--icon,
.v-sidebar-menu.vsm_white-theme .vsm--link_level-2 .vsm--icon {
  background-color: transparent;
  margin: 0 10px;
}
.v-sidebar-menu.vsm_white-theme .vsm--link_level-2 {
  padding-left: 40px;
}
.v-sidebar-menu.vsm_white-theme .vsm--link_level-2.vsm--link_active {
  color: var(--main-color);
}
.v-sidebar-menu.vsm_white-theme .vsm--link_level-1.vsm--link_exact-active,
.v-sidebar-menu.vsm_white-theme .vsm--link_level-1.vsm--link_active {
  box-shadow: none;
  background-color: var(--main-color);
  color: #fff;
  .vsm--icon {
    color: #fff;
    background-color: transparent;
  }
}
.v-sidebar-menu.vsm_white-theme.vsm_expanded .vsm--item_open .vsm--link_level-1,
.v-sidebar-menu.vsm_white-theme.vsm_expanded
  .vsm--item_open
  .vsm--link_level-1
  .vsm--icon {
  background-color: var(--main-color);
}
.v-sidebar-menu.vsm_white-theme .vsm--dropdown .vsm--list {
  background-color: transparent;
}
@media (max-width: 767px) {
  .ShowSideBar {
     left: 0;
  }
  .HideSideBar {
    left: -270px;
    z-index: 5;
  }
  .opcity1 {
    opacity: 1;
    display: inline-block;
  }
  .opcity0 {
    opacity: 0;
    display: none;
  }
}
</style>
