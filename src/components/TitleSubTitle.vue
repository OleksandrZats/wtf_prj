<template>
  <div class="titleSubTitle">
    <div
      class="titleSubTitle_subtitle_hr"
      :style="{ '--subtitle': `'` + titlesubtitle.subtitle + `'` }"
    ></div>
    <h1 class="titleSubTitle_header" v-text="titlesubtitle.title"></h1>
    <div class="titleSubTitle_hr"></div>
  </div>
</template>

<script>
export default {
  props: ["titlesubtitle"],
};
</script>

<style>
.titleSubTitle {
  display: flex;
  justify-content: flex-start;
  align-items: flex-end;
  width: 100%;
  color: #0e1c70;
}
.titleSubTitle_header {
  flex-shrink: 1;
  width: 35%;
  font-size: 55px;
  font-family: "GTCinetype";
  text-align: left;
  text-transform: uppercase;
}
.titleSubTitle_subtitle_hr {
  width: 27%;
  display: flex;
  border-bottom: 1px solid #0e1c70;
  margin-bottom: 1.5%;
  margin-right: 20px;
  justify-content: flex-end;
  align-items: flex-end;
}
.titleSubTitle_subtitle_hr:after {
  content: var(--subtitle);
  font-family: "GTCinetype";
  text-transform: uppercase;
  text-align: right;
  max-width: 200px;
}
.titleSubTitle_hr {
  width: 40%;
  display: inline-block;
  z-index: 0;
  position: absolute;
  right: 0;
  border-bottom: 1px solid #0e1c70;
  margin-bottom: 1.5%;
  margin-left: 0;
}
/* Large desktops and laptops */
@media (min-width: 1200px) {
  .titleSubTitle_header {
    font-size: 40px;
  }
  .titleSubTitle_subtitle_hr {
    min-width: 100px;
  }
  .titleSubTitle_subtitle_hr:after {
    font-size: 20px;
    max-width: 150px;
  }
}

/* Landscape tablets and medium desktops */
@media (min-width: 992px) and (max-width: 1199px) {
  .titleSubTitle {
    display: block;
  }
  .titleSubTitle_header {
    font-size: 45px;
    max-width: 100%;
    padding-left: 90px;
    padding-right: 130px;
  }
  .titleSubTitle_subtitle_hr {
    width: 100%;
    max-width: 100%;
  }
  .titleSubTitle_subtitle_hr:after {
    font-size: 30px;
    padding-right: 130px;
    max-width: none;
  }
}

/* Portrait tablets and small desktops */
@media (min-width: 769px) and (max-width: 991px) {
  .titleSubTitle {
    display: block;
  }
  .titleSubTitle_header {
    font-size: 45px;
    max-width: 100%;
    padding-left: 90px;
    padding-right: 130px;
  }
  .titleSubTitle_subtitle_hr {
    width: 100%;
    max-width: 100%;
  }
  .titleSubTitle_subtitle_hr:after {
    font-size: 30px;
    padding-right: 130px;
    max-width: none;
  }
}

/* Portrait phones and smaller */
@media (max-width: 768px) {
  .titleSubTitle {
    display: block;
  }
  .titleSubTitle_header {
    font-size: 35px;
    max-width: 100%;
    padding-left: 15px;
    padding-right: 18px;
  }
  .titleSubTitle_subtitle_hr {
    width: 100%;
    max-width: 100%;
  }
  .titleSubTitle_subtitle_hr:after {
    font-size: 20px;
    padding-right: 18px;
    max-width: none;
  }
}

/* Portrait phones and smaller */
@media (max-width: 480px) {
  .titleSubTitle_header {
    font-size: 25px;
    padding-left: 10px;
    padding-right: 13px;
  }
  .titleSubTitle_subtitle_hr:after {
    font-size: 15px;
    padding-right: 13px;
    max-width: none;
  }
}

/* Iphone 5 */
@media (max-width: 320px) {
  .titleSubTitle_header {
    font-size: 20px;
  }
  .titleSubTitle_subtitle_hr:after {
    max-width: none;
  }
}
</style>
