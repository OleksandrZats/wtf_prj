<template>
  <section class="smartContracts block scroll-to" @scroll="handleScroll">
    <div class="smartContracts_cont">
      <TitleSubTitle
        :titlesubtitle="{
          title: 'We provide the following services',
          subtitle: 'smart contracts audit',
        }"
      />
      <ul class="smartContracts_textList">
        <li class="textlist_item">
          Check against the latest attack vectors and give you a full pdf audit
          report.
        </li>
        <li class="textlist_item">Check against any logical errors.</li>
        <li class="textlist_item">
          We leverage a combination of static analysis, automated tools, and a
          robust manual review process to provide industry-leading security
          recommendations to project teams.
        </li>
        <li class="textlist_item">
          We assist project team’s in resolve any outstanding issues or
          implementing our recommendations.
        </li>
      </ul>
    </div>
  </section>
  <section class="smartContracts scroll-to" @scroll="handleScroll">
    <div class="note">
      <ul class="note_list">
        <li class="notelist_item">
          Normal price per audit $1000-$5000, time to deliver 1-3 days
        </li>
        <li class="notelist_item">100% Refund if we don’t meet the deadline</li>
        <li class="notelist_item">
          The audit is confidential. It’s up to you to do whatever you want with
          it after
        </li>
        <li class="notelist_item">
          We can only audit smart contracts that are on ethereum, binance smart
          chain (bsc), polygon (matic), fantom, avalance’s c-chain, harmony one,
          kucoin (kcc), huobi eco, arbitrum, or any other evm-compatible
          side-chain or l2 chain
        </li>
      </ul>
    </div>

    <div class="notice">
      <p class="notice_text">
        If no vulnerabilities or issues were found and your contract is 100
        correct then the audit is free
      </p>
    </div>
  </section>
  <section class="smartContracts scroll-to" @scroll="handleScroll">
    <div class="getStart_cont">
      <h2 class="getStart_head">How to get started:</h2>
      <ul class="getStart_list">
        <li class="getStartList_item">
          link to the deployed smart contract on the testnet/mainnet
        </li>
        <li class="getStartList_item">or link to github repo</li>
        <li class="getStartList_item">or the contracts zipped</li>
        <li class="getStartList_item">
          additionally if you have tests written it will greatly improve the
          audit delivery time.
        </li>
      </ul>
      <div class="quote">
        <p class="quote_text">Get a free quote</p>
        <div class="links">
          <a href="" class="link"
            ><img src="../assets/Telegram.svg" alt="Telegram" /></a
          ><a href="" class="link"
            ><img src="../assets/Mail.svg" alt="Mail"
          /></a>
        </div>
      </div>
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
.smartContracts {
  padding: 9% 0 9%;
  width: 100%;
  height: 100vh;
  color: #0e1c70;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  justify-content: space-between;
}

.smartContracts_cont {
  width: 100%;
  color: #0e1c70;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
}

.smartContracts_textList {
  font-size: 30px;
  font-family: "GTAlpina";
  line-height: 1.162;
  width: 46%;
  padding-left: 10px;
  text-align: left;
}

.smartContracts_textList {
  width: 46%;
  list-style: none;
  margin-top: 15px;
}

.textlist_item {
  display: flex;
  margin-bottom: 10px;
  line-height: 1.162;
}
.textlist_item::before {
  content: "\2192";
  margin-right: 5px;
  display: block;
}

.note {
  width: 60%;
  display: flex;
  align-items: flex-start;
}

.note::before {
  font-size: 30px;
  font-family: "GTCinetype";
  color: rgb(14, 28, 112);
  text-transform: uppercase;

  display: inline-block;
  padding: 20px 10px;
  min-width: 200px;
  border-radius: 50%;
  border: 1px solid;
  background-color: #fff;
  content: "note that";
  text-transform: uppercase;
  flex-grow: 1;
}

.note_list {
  padding-top: 20px;
  padding-left: 30px;
  list-style: none;
}
.notelist_item {
  font-size: 20px;
  font-family: "GTCinetype";
  color: rgb(14, 28, 112);
  line-height: 1.259;
  display: flex;
  flex-direction: row;
  text-align: left;
  padding-bottom: 10px;
}
.notelist_item::before {
  content: "\2192";
  margin-right: 20px;
  display: inline-block;
}

.notice {
  margin-top: 2%;
  width: 45%;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  justify-self: flex-end;
}

.notice::before {
  content: "";
  position: absolute;
  width: 50px;
  height: 100%;
  border-left: 1px solid;
  border-radius: 40%;
  left: 0px;
}
.notice::after {
  content: "";
  position: absolute;
  width: 50px;
  height: 100%;
  border-right: 1px solid;
  border-radius: 40%;
  right: -5px;
}
.notice_text {
  font-size: 24px;
  font-family: "GTCinetype";
  color: rgb(14, 28, 112);
  text-transform: uppercase;
  line-height: 1.259;
  text-align: center;
}

.getStart_cont {
  width: 45%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.getStart_head {
  font-size: 45px;
  font-family: "GTCinetype";
  color: rgb(14, 28, 112);
  text-transform: uppercase;
  text-align: left;
}

.getStart_list {
  margin-top: 25px;
  list-style: none;
  text-align: left;
}

.getStartList_item {
  margin-bottom: 10px;
  font-size: 27px;
  font-family: "GTAlpina";
  color: rgb(14, 28, 112);
  line-height: 1.162;
  display: flex;
  flex-direction: row;
  text-align: left;
}

.getStartList_item::before {
  content: "\2192";
  margin-right: 20px;
  display: inline-block;
}

.quote {
  background-color: #b3e6bc;
  border-width: 1px;
  border-color: rgb(14, 28, 112);
  border-style: solid;
  border-radius: 10px;
  min-width: 350px;
  padding: 25px 30px 30px;

  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;

  align-self: center;
  margin-top: 12%;
}

.quote_text {
  font-size: 27px;
  font-family: "GTCinetype";
  color: rgb(14, 28, 112);
  text-transform: uppercase;
  margin-bottom: 33px;
}

.links {
  display: flex;
  justify-content: space-between;
}

.link {
  width: 70px;
}
.link:first-child {
  margin-right: 25px;
}

.link img {
  width: 70px;
}

/* Large desktops and laptops */
@media (min-width: 1200px) {
}

/* Landscape tablets and medium desktops */
@media (min-width: 992px) and (max-width: 1199px) {
  .smartContracts {
    padding-top: 13%;
  }
  .smartContracts_textList {
    padding-top: 5%;
    font-size: 27px;
    width: 84%;
    text-align: left;
  }
  .note {
    width: 84%;
  }
  .getStart_cont {
    width: 84%;
  }
  .quote {
    max-width: 40%;
    padding: 12px 20px 20px;
  }
}

/* Portrait tablets and small desktops */
@media (min-width: 769px) and (max-width: 991px) {
  .smartContracts {
    padding-top: 13%;
  }
  .smartContracts_textList {
    padding-top: 5%;
    font-size: 27px;
    width: 84%;
    text-align: left;
  }
  .note {
    width: 84%;
  }
  .note::before {
    font-size: 25px;
    padding: 10px 5px;
    min-width: 150x;
  }
  .notice {
    width: 70%;
    padding-left: 2%;
    padding-right: 2%;
  }
  .notice_text {
    font-size: 20px;
  }
  .getStart_cont {
    width: 84%;
  }
  .quote {
    max-width: 40%;
    padding: 12px 20px 20px;
  }
}

/* Portrait phones and smaller */
@media (max-width: 768px) {
  .smartContracts {
    padding-top: 13%;
  }
  .smartContracts_textList {
    padding-top: 5%;
    font-size: 27px;
    width: 84%;
    text-align: left;
  }
  .note {
    width: 84%;
  }
  .note::before {
    font-size: 25px;
    padding: 10px 5px;
    min-width: 150x;
  }
  .notice {
    width: 70%;
    padding-left: 2%;
    padding-right: 2%;
  
  margin-bottom: 10%;
  }
  .notice_text {
    font-size: 20px;
  }
  .getStart_cont {
    width: 84%;
  }
  .getStart_head {
    font-size: 32px;
  }
  .quote {
    max-width: 40%;
    padding: 10px 20px 20px;
  }
}

/* Portrait phones and smaller */
@media (max-width: 480px) {
  .smartContracts {
    padding: 30% 0 13%;
  }
  .smartContracts_textList {
    padding-top: 5%;
    font-size: 23px;
    width: 97%;
    text-align: left;
  }
  .note {
    width: 84%;
    flex-direction: column;
  }
  .note::before {
    font-size: 20px;
    padding: 10px 5px;
    min-width: 150x;
  }
  .note_list {
    padding-left: 0;
  }
  .notelist_item {
    font-size: 15px;
  }
  .notice_text {
    font-size: 15px;
  }
  .getStartList_item {
    font-size: 20px;
  }
  .getStart_head {
    font-size: 25px;
  }
  .quote {
    min-width: 90%;
    margin-top: 5%;
    padding: 10px 15px 10px;
  }
  .quote_text {
    font-size: 25px;
    margin-bottom: 10px;
  }
}

/* Iphone 5 */
@media (max-width: 320px) {
  .textlist_item {
    font-size: 17px;
  }
  .notelist_item {
    font-size: 13px;
  }
  .notice {
    width: 80%;
  }
  .notice_text {
    font-size: 13px;
  }
  .getStart_head {
    font-size: 20px;
  }
  .getStartList_item {
    font-size: 17;
  }
  .quote {
    min-width: 100%;
    margin-top: 40%;
    padding: 5px;
  }
  .quote_text {
    font-size: 20px;
    margin-bottom: 10px;
  }
  .link img {
    width: 50px;
  }
}
</style>
