<template>
  <Header />
  <AboutUs class="123" />
  <AboutUs class="123" />
  <AboutUs class="123" />
</template>

<script>
import Header from "./components/Header.vue";
import AboutUs from "./components/AboutUs.vue";

export default {
  name: "App",
  data() {
    return {
      inMove: false,
      activeSection: 0,
      offsets: [],
      touchStartY: 0,
    };
  },
  components: {
    Header,
    AboutUs,
  },
  methods: {
    calculateSectionOffsets() {
      setTimeout(() => {
        let sections = document.getElementsByClassName("123");
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
      this.activeSection--;

      //if (this.activeSection < 0) this.activeSection = this.offsets.length - 1; //For infinit-scroll
      if (this.activeSection < 0) this.activeSection = 0;

      this.scrollToSection(this.activeSection, true);
    },
    moveUp() {
      this.inMove = true;
      this.activeSection++;

      //if (this.activeSection > this.offsets.length - 1) this.activeSection = 0; //For infinit-scroll
      if (this.activeSection > this.offsets.length - 1) this.activeSection = this.offsets.length - 1;

      this.scrollToSection(this.activeSection, true);
    },
    scrollToSection(id, force = false) {
      if (this.inMove && !force) return false;

      this.activeSection = id;
      this.inMove = true;

      document
        .getElementsByClassName("aboutUs")
        [id].scrollIntoView({ behavior: "smooth" });
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

    window.addEventListener("DOMMouseScroll", this.handleMouseWheelDOM); // Mozilla Firefox
    window.addEventListener("mousewheel", this.handleMouseWheel, {
      passive: false,
    }); // Other browsers

    window.addEventListener("touchstart", this.touchStart, { passive: false }); // mobile devices
    window.addEventListener("touchmove", this.touchMove, { passive: false }); // mobile devices
  },
  destroyed() {
    window.removeEventListener("mousewheel", this.handleMouseWheel, {
      passive: false,
    }); // Other browsers
    window.removeEventListener("DOMMouseScroll", this.handleMouseWheelDOM); // Mozilla Firefox

    window.removeEventListener("touchstart", this.touchStart); // mobile devices
    window.removeEventListener("touchmove", this.touchMove); // mobile devices
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
html {
  background: url("./assets/Background.svg") center center;
  background-size: cover;
  background-color: #d9dbda;
}
@media only screen and (max-width: 1000px) {
  html {
    background-size: 400%;
    background-position: center;
  }
}
</style>
