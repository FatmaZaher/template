<template>
  <sidebar-menu
    :menu="SideBarMenu"
    width="270px"
    widthCollapsed="50px"
    theme="white-theme"
  >
    <div slot="header">
      <div class="user-card d-flex w-100 justify-content-center py-4">
        <div class="image">
          <img src="~/assets/images/Photo.png" alt="Person image" />
        </div>
        <div class="text mr-3 d-flex align-items-center">
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
    }
  },
  mounted() {
    this.SideBarMenu = SideBarItems
  },
}
</script>
<style lang="scss">
.v-sidebar-menu {
  right: 30px;
  text-align: right;
  top: 30px;
  bottom: 30px;
  padding: 0 10px;
  border-radius: 20px;
  box-shadow: 0 3px 36px 0 rgb(0 0 0 / 10%);
  margin-left: 35px;
  .vsm--link {
    font-size: 14px;
    padding: 5px;
    padding-right: 40px;
    margin: 5px;
    border-radius: 25px;
  }
  .vsm--toggle-btn {
    display: none;
  }
}
.v-sidebar-menu.vsm_white-theme .vsm--link_level-1 .vsm--icon {
  background-color: transparent;
  margin-left: 10px;
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
</style>
