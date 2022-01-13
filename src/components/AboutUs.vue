<template>
  <section class="aboutUs block scroll-to" @scroll="handleScroll">
    <div class="aboutUs_cont">
      <TitleSubTitle
        :titlesubtitle="{
          title: 'Blockchain and Smart Contracts Software Development',
          subtitle: 'about us',
        }"
      />
      <p class="aboutUs_text">
        We utilize our expertise and passion to build blockchain based solutions
        to empower businesses and inventive entrepreneurs to automate
        operations, integrate and upgrade novel and legacy systems, or build
        from conception to delivery that drive measurable results.
      </p>
    </div>

    <div class="subtextCont">
      <p class="subtextCont_text">Let’s build the smart contracts you need!</p>
    </div>
  </section>
</template>

<script>
import TitleSubTitle from "./TitleSubTitle.vue";

export default {
  data() {
    return {};
  },
  methods: {},
  components: {
    TitleSubTitle,
  },
};
</script>

<style>
.aboutUs {
  padding: 7% 0 7%;
  width: 100%;
  height: 100vh;
  color: #0e1c70;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  justify-content: space-between;
}

.aboutUs_cont {
  width: 100%;
  color: #0e1c70;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
}

.aboutUs_text {
  font-size: 30px;
  font-family: "GTAlpina";
  line-height: 1.162;
  width: 46%;
  padding-left: 10px;
  text-align: left;
  padding-top: 2%;
}

.subtextCont {
  max-width: 40%;
  padding: 40px 0 20px;
  border: solid 1px #0e1c70;
  border-radius: 50%;
  display: flex;
  align-items: center;
  position: relative;
  text-align: center;
}
.subtextCont::after {
  content: "";
  width: 37px;
  height: 90px;
  display: block;
  background: url("../assets/Arrow.svg") center center no-repeat;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  bottom: -55%;
}

.subtextCont_text {
  font-size: 30px;
  font-family: "GTCinetype";
  line-height: 1.162;
  text-align: center;
}

@media (min-width: 2500px) {
  .subtextCont{
    padding: 50px 40px;
  }
}

/* Large desktops and laptops */
@media (min-width: 1200px) {
}

/* Landscape tablets and medium desktops */
@media (min-width: 992px) and (max-width: 1199px) {
  .aboutUs {
    padding-top: 13%;
  }
  .aboutUs_text {
    padding-top: 5%;
    font-size: 27px;
    width: 84%;
    text-align: left;
  }
  .subtextCont {
    padding: 40px 10px 30px;
    max-width: 50%;
  }
  .subtextCont_text {
    font-size: 27px;
  }
  .subtextCont::after {
    bottom: -53%;
  }
}

/* Portrait tablets and small desktops */
@media (min-width: 769px) and (max-width: 991px) {
  .aboutUs {
    padding-top: 13%;
  }
  .aboutUs_text {
    padding-top: 5%;
    font-size: 26px;
    width: 80%;
    text-align: left;
  }
  .subtextCont {
    padding: 40px 10px 30px;
    max-width: 50%;
  }
  .subtextCont_text {
    font-size: 27px;
  }
  .subtextCont::after {
    bottom: -43%;
  }
}

/* Portrait phones and smaller */
@media (max-width: 768px) {
  .aboutUs {
    padding-top: 13%;
  }
  .aboutUs_text {
    padding-top: 5%;
    font-size: 26px;
    width: 97%;
    text-align: left;
  }
  .subtextCont {
    padding: 40px 10px 30px;
    max-width: 80%;
    margin-bottom: 15%;
  }
  .subtextCont_text {
    font-size: 27px;
  }
  .subtextCont::after {
    bottom: -53%;
  }
}

/* Portrait phones and smaller */
@media (max-width: 480px) {
  .aboutUs {
    padding: 30% 0 13%;
  }
  .aboutUs_text {
    padding-top: 5%;
    font-size: 23px;
    width: 97%;
    text-align: left;
  }
  .subtextCont {
    padding: 20px 5px 15px;
    max-width: 70%;
  }
  .subtextCont_text {
    font-size: 17px;
  }
  .subtextCont::after {
    bottom: -90%;
    width: 30px;
  }
}

/* Iphone 5 */
@media (max-width: 320px) {
  .aboutUs_text {
    padding-top: 10%;
  }
  .subtextCont::after {
    bottom: -66%;
    width: 25px;
  }
}
</style>
