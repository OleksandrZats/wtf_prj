<template>
  <Header :activeLink="activeLink" @scrollTo="scroll" @menuActive="menuActive" />
  <main :class="{ 'scrollOff' : !isMenuInActive }" :style="{top:'-' + activeSection * 100 + 'vh'}">
  <AboutUs />
  <SmartContractsAudit />
  <CryptoAssets />
  <Blockchain />
  <NftProjects />
  <Tokenomics />
  <DaoPage />
  </main>
</template>

<script>
import Header from "./components/Header.vue";
import AboutUs from "./components/AboutUs.vue";
import SmartContractsAudit from "./components/SmartContractsAudit.vue";
import CryptoAssets from "./components/CryptoAssets.vue";
import Blockchain from "./components/Blockchain.vue";
import NftProjects from "./components/NftProjects.vue";
import Tokenomics from "./components/Tokenomics.vue";
import DaoPage from "./components/DaoPage.vue";

export default {
  name: "App",
  data() {
    return {
      inMove: false,
      activeSection: 0,
      activeBlock: 0,
      offsets: [],
      touchStartY: 0,
      current: 0,
      activeLink: [true, false, false, false, false, false, false],
      isMenuInActive: true,
    };
  },
  components: {
    Header,
    AboutUs,
    SmartContractsAudit,
    CryptoAssets,
    Blockchain,
    NftProjects,
    Tokenomics,
    DaoPage,
  },
  mounted: function () {
    this.scrollToSection(0); //method1 will execute at pageload
  },
  methods: {
    menuActive(i){
      this.isMenuInActive = i.active
      console.log(this.isMenuInActive)
    },
    calculateSectionOffsets() {
      setTimeout(() => {
        let sections = document.getElementsByClassName("scroll-to");
        let length = sections.length;

        for (let i = 0; i < length; i++) {
          let sectionOffset = sections[i].offsetTop;
          this.offsets.push(sectionOffset);
        }
      }, 250);
    },
    handleMouseWheel: function (e) {
      if (e.wheelDelta < 30 && !this.inMove) {
        this.moveUp();
      } else if (e.wheelDelta > 30 && !this.inMove) {
        this.moveDown();
      }

      e.preventDefault();
      return false;
    },
    handleMouseWheelDOM: function (e) {
      if (e.detail > 0 && !this.inMove) {
        this.moveUp();
      } else if (e.detail < 0 && !this.inMove) {
        this.moveDown();
      }

      return false;
    },
    moveDown() {
      this.inMove = true;
      let temp = this.activeSection--;

      //if (this.activeSection < 0) this.activeSection = this.offsets.length - 1; //For infinit-scroll
      if (this.activeSection < 0) this.activeSection = 0;

      let tempArr = [
        ...document.getElementsByClassName("scroll-to")[this.activeSection]
          .classList,
      ];
      document
        .getElementsByClassName("scroll-to")
        [temp].classList.forEach((elem) => tempArr.push(elem));
      tempArr = [...new Set(tempArr)];
      if (
        tempArr.length >
        document.getElementsByClassName("scroll-to")[this.activeSection]
          .classList.length
      )
        this.activeBlock--;

      this.activeLink = this.activeLink.map((el) => (el = false));
      this.activeLink[this.activeBlock] = !this.activeLink[this.activeBlock];

      this.scrollToSection(this.activeSection, true);
    },
    moveUp() {
      this.inMove = true;
      let temp = this.activeSection++;

      //if (this.activeSection > this.offsets.length - 1) this.activeSection = 0; //For infinit-scroll
      if (this.activeSection > this.offsets.length - 1)
        this.activeSection = this.offsets.length - 1;

      if (
        document
          .getElementsByClassName("scroll-to")
          [this.activeSection].classList.contains("block") &&
        !(temp >= this.offsets.length - 1)
      )
        this.activeBlock++;

      this.activeLink = this.activeLink.map((el) => (el = false));
      this.activeLink[this.activeBlock] = !this.activeLink[this.activeBlock];

      this.scrollToSection(this.activeSection, true);
    },
    scroll(i) {
      if (this.activeBlock != i.block) {
        this.scrollToSection(i.section);

        this.activeLink = this.activeLink.map((el) => (el = false));
        this.activeLink[i.block] = !this.activeLink[i.block];

        this.activeBlock = i.block;
      }
    },
    scrollToSection(id, force = false) {
      if (this.inMove && !force) return false;
      this.activeSection = id;
      this.inMove = true;
      // document
      //   .getElementsByClassName("scroll-to")
      //   [id].scrollIntoView({ behavior: "smooth" });
      setTimeout(() => {
        this.inMove = false;
      }, 400);
    },
    touchStart(e) {
      e.preventDefault();

      this.touchStartY = e.touches[0].clientY;
    },
    touchMove(e) {
      if (this.inMove) return false;
      e.preventDefault();

      const currentY = e.touches[0].clientY;

      if (this.touchStartY < currentY) {
        this.moveDown();
      } else {
        this.moveUp();
      }

      this.touchStartY = 0;
      return false;
    },
  },
  created() {
    this.calculateSectionOffsets();
    setTimeout(() => {
    document.getElementsByTagName('main')[0].addEventListener("DOMMouseScroll", this.handleMouseWheelDOM); // Mozilla Firefox
    document.getElementsByTagName('main')[0].addEventListener("mousewheel", this.handleMouseWheel, {
      passive: false,
    }); // Other browsers

    document.getElementsByTagName('main')[0].addEventListener("touchstart", this.touchStart, { passive: false }); // mobile devices
    document.getElementsByTagName('main')[0].addEventListener("touchmove", this.touchMove, { passive: false }); // mobile devices
    }, 250)
  },
  destroyed() {
    setTimeout(() => {
    document.getElementsByTagName('main')[0].removeEventListener("mousewheel", this.handleMouseWheel, {
      passive: false,
    }); // Other browsers
    document.getElementsByTagName('main')[0].removeEventListener("DOMMouseScroll", this.handleMouseWheelDOM); // Mozilla Firefox

    document.getElementsByTagName('main')[0].removeEventListener("touchstart", this.touchStart); // mobile devices
    document.getElementsByTagName('main')[0].removeEventListener("touchmove", this.touchMove); // mobile devices
    }, 250)
  },
};
</script>

<style>
@font-face {
  font-family: "GTCinetype";
  src: url("./fonts/Cinetype/GT-Cinetype-Mono.ttf") format("truetype");
  font-style: normal;
  font-weight: normal;
}
@font-face {
  font-family: "GTAlpina";
  src: url("./fonts/Alpina/GT-Alpina-Standard-Thin.ttf") format("truetype");
  font-style: normal;
  font-weight: normal;
}
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: transparent;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
::-webkit-scrollbar { /* chrome based */
    width: 0px;  /* ширина scrollbar'a */
    background: transparent;  /* опционально */
}
html {
    -ms-overflow-style: none;  /* IE 10+ */
    scrollbar-width: none; /* Firefox */

  background: url("./assets/Background.svg") center center;
  background-size: cover;
  background-color: #d9dbda;
}
main{
  position: relative;
  transition-property: top;
  transition-duration: 1s;
}
.scrollOff{
  display: none;
}

@media (min-width: 2500px) {
  html {
    background-size: 250%;
  }
}
@media only screen and (max-width: 1000px) {
  html {
    background-size: 400%;
    background-position: center;
  }
}
</style>
