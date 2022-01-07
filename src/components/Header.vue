<template>
  <div class="header">
    <img class="header_logo" src="../assets/logo.png" alt="" />
    <button @click="setActiveMenu" class="header_burger">
      <div
        :class="{ 'burger_line-active': activeBurger }"
        class="burger_line"
      ></div>
    </button>
  </div>
  <nav :class="{ 'mainmenu-active': activeMenu }" class="mainmenu">
    <ul class="mainmenu_list">
      <li class="list_item">
        <a
          :class="{ 'item_link-active': activeLink[0] }"
          class="item_link"
          @click="setLinkActive(0)"
          >About us</a
        >
      </li>
      <li class="list_item">
        <a
          :class="{ 'item_link-active': activeLink[1] }"
          class="item_link"
          @click="setLinkActive(1)"
          >Smart contracts audit</a
        >
      </li>
      <li class="list_item">
        <a
          :class="{ 'item_link-active': activeLink[2] }"
          class="item_link"
          @click="setLinkActive(2)"
          >Crypto assets recovery</a
        >
      </li>
      <li class="list_item">
        <a
          :class="{ 'item_link-active': activeLink[3] }"
          class="item_link"
          @click="setLinkActive(3)"
          >Blockchain forensics</a
        >
      </li>
      <li class="list_item">
        <a
          :class="{ 'item_link-active': activeLink[4] }"
          class="item_link"
          @click="setLinkActive(4)"
          >Nft projects</a
        >
      </li>
      <li class="list_item">
        <a
          :class="{ 'item_link-active': activeLink[5] }"
          class="item_link"
          @click="setLinkActive(5)"
          >Tokenomics</a
        >
      </li>
      <li class="list_item">
        <a
          :class="{ 'item_link-active': activeLink[6] }"
          class="item_link"
          @click="setLinkActive(6)"
          >Dao</a
        >
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      activeMenu: false,
      activeBurger: false,
      activeLink: [true, false, false, false, false, false, false],
    };
  },
  methods: {
    setActiveMenu() {
      this.activeMenu = !this.activeMenu;
      this.activeBurger = !this.activeBurger;
    },
    setLinkActive(pos) {
      this.setActiveMenu();
      this.activeLink = this.activeLink.map((el) => (el = false));
      this.activeLink[pos] = !this.activeLink[pos];
    },
  },
};
</script>

<style>
.header {
  background-color: #b3e6bc;
  width: 100%;
  padding: 14px 432px 14px 240px;
  position: relative;
  display: flex;
  justify-content: flex-end;
}
.header_logo {
  position: absolute;
  top: -42px;
  left: 240px;
}
.header_burger {
  width: 41px;
  height: 41px;
  border-radius: 50%;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  background-color: transparent;
  border: solid 1px;
  border-color: #0e2963;

  box-shadow: none;
}

.burger_line {
  position: relative;
  display: flex;
  width: 23px;
  height: 2px;
  background-color: #0e2963;
}
.burger_line::before {
  position: absolute;
  top: -6px;
  content: "";
  width: 23px;
  height: 2px;
  background-color: #0e2963;
}
.burger_line::after {
  position: absolute;
  top: 6px;
  content: "";
  width: 23px;
  height: 2px;
  background-color: #0e2963;
}
.burger_line-active {
  background-color: transparent;
}
.burger_line-active::before {
  top: 0;
  transform: rotate(45deg);
}
.burger_line-active::after {
  top: 0px;
  transform: rotate(-45deg);
}

.header_burger:hover {
  background-color: #0e2963;
  cursor: pointer;
}
.header_burger:hover .burger_line {
  background-color: #fff;
}
.header_burger:hover .burger_line::before {
  background-color: #fff;
}
.header_burger:hover .burger_line::after {
  background-color: #fff;
}
.header_burger:hover .burger_line-active {
  background-color: transparent;
}

.mainmenu {
  background-color: #b3e6bc;
  height: 100vh;
  width: 100%;

  display: none;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;

  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 14%;
  z-index: -1;
}
.mainmenu-active {
  display: flex;
}

.mainmenu_list {
  list-style: none;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
}

.item_link {
  text-decoration: none;
  color: #0e1c70;
  cursor: pointer;

  font-size: 55px;
  line-height: 73px;
  font-family: "GTCinetype";
  text-transform: uppercase;
}
.item_link-active::before {
  content: "\2192";
  margin-right: 32px;
}
</style>
