<template>
  <section class="blockchain block scroll-to" @scroll="handleScroll">
    <div class="blockchain_cont">
      <TitleSubTitle
        :titlesubtitle="{
          title: 'Lorem ipsum dolor sit amet consectetur',
          subtitle: 'blockchain forensics',
        }"
      />
      <p class="blockchain_text">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla beatae,
        nesciunt, quasi facere aliquid ratione natus perferendis impedit aliquam
        eum nemo quidem voluptatibus, labore autem explicabo deleniti aut
        corporis debitis. Natus eius ducimus officia similique totam, odit eum
        ipsum quo vitae debitis neque atque expedita repellat hic qui
        consequuntur illo!
      </p>
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
.blockchain {
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

.blockchain_cont {
  width: 100%;
  color: #0e1c70;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
}

.blockchain_text {
  font-size: 30px;
  font-family: "GTAlpina";
  line-height: 1.162;
  width: 46%;
  padding-left: 10px;
  text-align: left;
  padding-top: 2%;
}
/* Large desktops and laptops */
@media (min-width: 1200px) {
}

/* Landscape tablets and medium desktops */
@media (min-width: 992px) and (max-width: 1199px) {
  .blockchain {
    padding-top: 13%;
  }
  .blockchain_text {
    padding-top: 5%;
    font-size: 27px;
    width: 84%;
    text-align: left;
  }
}

/* Portrait tablets and small desktops */
@media (min-width: 769px) and (max-width: 991px) {
  .blockchain {
    padding-top: 13%;
  }
  .blockchain_text {
    padding-top: 5%;
    font-size: 26px;
    width: 80%;
    text-align: left;
  }
}

/* Portrait phones and smaller */
@media (max-width: 768px) {
  .blockchain {
    padding-top: 13%;
  }
  .blockchain_text {
    padding-top: 5%;
    font-size: 26px;
    width: 97%;
    text-align: left;
  }
}

/* Portrait phones and smaller */
@media (max-width: 480px) {
  .blockchain {
    padding: 30% 0 13%;
  }
  .blockchain_text {
    padding-top: 5%;
    font-size: 23px;
    width: 97%;
    text-align: left;
  }
}

/* Iphone 5 */
@media (max-width: 320px) {
  .blockchain_text {
    padding-top: 10%;
  }
}
</style>
