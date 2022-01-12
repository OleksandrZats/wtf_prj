<template>
  <div class="header">
    <img class="header_logo" src="../assets/logo.png" alt="" />
    <button
      @click="setActiveMenu()"
      @touchend="setActiveMenu()"
      class="header_burger"
    >
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
          @click="
            setLinkActive(0), scrollToSectionMenu('aboutUs'), changeSection()
          "
          @touchend="
            setLinkActive(0), scrollToSectionMenu('aboutUs'), changeSection()
          "
          >About us</a
        >
      </li>
      <li class="list_item">
        <a
          :class="{ 'item_link-active': activeLink[1] }"
          class="item_link"
          @click="
            setLinkActive(1),
              scrollToSectionMenu('smartContracts'),
              changeSection()
          "
          @touchend="
            setLinkActive(0),
              scrollToSectionMenu('smartContracts'),
              changeSection()
          "
          >Smart contracts audit</a
        >
      </li>
      <li class="list_item">
        <a
          :class="{ 'item_link-active': activeLink[2] }"
          class="item_link"
          @click="
            setLinkActive(2),
              scrollToSectionMenu('cryptoAssets'),
              changeSection()
          "
          @touchend="
            setLinkActive(0),
              scrollToSectionMenu('cryptoAssets'),
              changeSection()
          "
          >Crypto assets recovery</a
        >
      </li>
      <li class="list_item">
        <a
          :class="{ 'item_link-active': activeLink[3] }"
          class="item_link"
          @click="
            setLinkActive(3), scrollToSectionMenu('blockchain'), changeSection()
          "
          @touchend="
            setLinkActive(0), scrollToSectionMenu('blockchain'), changeSection()
          "
          >Blockchain forensics</a
        >
      </li>
      <li class="list_item">
        <a
          :class="{ 'item_link-active': activeLink[4] }"
          class="item_link"
          @click="
            setLinkActive(4),
              scrollToSectionMenu('nftProjects'),
              changeSection()
          "
          @touchend="
            setLinkActive(0),
              scrollToSectionMenu('nftProjects'),
              changeSection()
          "
          >Nft projects</a
        >
      </li>
      <li class="list_item">
        <a
          :class="{ 'item_link-active': activeLink[5] }"
          class="item_link"
          @click="
            setLinkActive(5), scrollToSectionMenu('tokenomics'), changeSection()
          "
          @touchend="
            setLinkActive(0), scrollToSectionMenu('tokenomics'), changeSection()
          "
          >Tokenomics</a
        >
      </li>
      <li class="list_item">
        <a
          :class="{ 'item_link-active': activeLink[6] }"
          class="item_link"
          @click="setLinkActive(6), scrollToSectionMenu('dao'), changeSection()"
          @touchend="
            setLinkActive(0), scrollToSectionMenu('dao'), changeSection()
          "
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
      name: "aboutUs",
    };
  },
  props: ["activeLink"],
  emits: ["scrollTo"],
  methods: {
    setActiveMenu() {
      this.activeMenu = !this.activeMenu;
      this.activeBurger = !this.activeBurger;
    },
    setLinkActive(pos) {
      this.setActiveMenu();
    },
    scrollToSectionMenu(name, force = false) {
      this.name = name;
      document
        .getElementsByClassName(name)[0]
        .scrollIntoView({ behavior: "smooth" });
      setTimeout(() => {
        this.inMove = false;
      }, 400);
    },
    changeSection() {
      let number = 0;
      let numberBlocks = 0;
      let elements = document.getElementsByClassName("scroll-to");
      let blocks = document.getElementsByClassName("block");
      for (let index = 0; index < elements.length; index++) {
        if (
          elements[index].classList.contains(this.name) &&
          elements[index].classList.contains("block")
        ) {
          number = index;
          break;
        }
      }
      for (let index = 0; index < blocks.length; index++) {
        if (blocks[index].classList.contains(this.name)) {
          numberBlocks = index;
          break;
        }
      }
      this.$emit("scrollTo", {
        section: number,
        block: numberBlocks,
      });
    },
  },
};
</script>

<style>
.header {
  background-color: #b3e6bc;
  width: 100%;
  padding: 14px 432px 14px 240px;
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  justify-content: flex-end;
  z-index: 10;
}
.header_logo {
  position: absolute;
  top: -50%;
  left: 240px;
  max-width: 10%;
}
.header_burger {
  width: 40px;
  height: 40px;
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
  padding: 0px 3px;
}

.burger_line {
  position: relative;
  display: flex;
  width: 23px;
  height: 2px;
  background-color: #0e2963;
  cursor: pointer;
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

.mainmenu {
  background-color: #b3e6bc;
  height: 100vh;
  width: 100%;

  display: none;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;

  padding: 12%;
  z-index: 1;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
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

  font-size: 3vw;
  line-height: 4vw;
  font-family: "GTCinetype";
  text-transform: uppercase;
}
.item_link-active::before {
  content: "\2192";
  margin-right: 32px;
}

/* Large desktops and laptops */
@media (min-width: 1200px) {
  .header {
    padding: 10px 20px;
  }
  .header_logo {
    top: -35px;
    left: 25px;
    max-width: 12%;
  }

  .item_link {
    font-size: 4vw;
    line-height: 5vw;
  }
  .mainmenu {
    align-items: center;
    justify-content: flex-start;
    padding: 10% 5px;
  }
  .mainmenu_list {
    list-style: none;

    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
  }

  .item_link-active::before {
    margin-right: 5px;
  }
}

/* Landscape tablets and medium desktops */
@media (min-width: 992px) and (max-width: 1199px) {
  .header {
    padding: 10px 20px;
  }
  .header_logo {
    top: -20px;
    left: 25px;
    max-width: 15%;
  }

  .item_link {
    font-size: 4vw;
    line-height: 5vw;
  }
  .mainmenu {
    align-items: center;
    justify-content: flex-start;
    padding: 10% 5px;
  }
  .mainmenu_list {
    list-style: none;

    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
  }

  .item_link-active::before {
    margin-right: 5px;
  }
}

/* Portrait tablets and small desktops */
@media (min-width: 769px) and (max-width: 991px) {
  .header {
    padding: 10px 20px;
  }
  .header_logo {
    top: -20px;
    left: 25px;
    max-width: 15%;
  }

  .item_link {
    font-size: 4vw;
    line-height: 5vw;
  }
  .mainmenu {
    align-items: center;
    justify-content: flex-start;
    padding: 10% 5px;
  }
  .mainmenu_list {
    list-style: none;

    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
  }

  .item_link-active::before {
    margin-right: 5px;
  }
}

/* Portrait phones and smaller */
@media (max-width: 768px) {
  .header {
    padding: 10px 20px;
  }
  .header_logo {
    top: -20px;
    left: 25px;
    max-width: 15%;
  }

  .item_link {
    font-size: 4vw;
    line-height: 5vw;
  }
  .mainmenu {
    align-items: center;
    justify-content: flex-start;
    padding: 10% 5px;
  }
  .mainmenu_list {
    list-style: none;

    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
  }

  .item_link-active::before {
    margin-right: 5px;
  }
}

/* Portrait phones and smaller */
@media (max-width: 480px) {
  .mainmenu {
    align-items: center;
    justify-content: flex-start;
    padding: 30% 5px;
  }
  .item_link {
    font-size: 6.5vw;
    line-height: 10vw;
  }
  .header_logo {
    top: -20px;
    left: 25px;
    max-width: 30%;
  }
}

/* Iphone 5 */
@media (max-width: 320px) {
  .item_link {
    font-size: 6vw;
    line-height: 10vw;
  }
  .header_logo {
    top: -18px;
    left: 25px;
    max-width: 30%;
  }
}

@media (hover: hover) {
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
}
</style>
