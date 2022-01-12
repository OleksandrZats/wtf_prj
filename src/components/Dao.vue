<template>
  <section class="dao scroll-to" @scroll="handleScroll">
    <div class="dao_cont">
      <TitleSubTitle
        :titlesubtitle="{
          title: 'Blockchain and Smart Contracts Software Development',
          subtitle: 'dao',
        }"
      />
      <p class="dao_text">
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
  props: ["titlesubtitle"],
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
.dao {
  padding: 9% 0 5%;
  width: 100%;
  height: 100vh;
  color: #0e1c70;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
}

.dao_cont {
  width: 100%;
  height: 80vh;
  color: #0e1c70;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
}

.dao_text {
  font-size: 30px;
  font-family: "GTAlpina";
  line-height: 1.162;
  width: 46%;
  padding-left: 10px;
  text-align: left;
}

.subtextCont {
  max-width: 35%;
  padding: 40px 0 20px;
  border: solid 1px black;
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
/* Large desktops and laptops */
@media (min-width: 1200px) {
}

/* Landscape tablets and medium desktops */
@media (min-width: 992px) and (max-width: 1199px) {
}

/* Portrait tablets and small desktops */
@media (min-width: 769px) and (max-width: 991px) {
}

/* Portrait phones and smaller */
@media (max-width: 768px) {
}

/* Portrait phones and smaller */
@media (max-width: 480px) {
}

/* Iphone 5 */
@media (max-width: 320px) {
}
</style>
