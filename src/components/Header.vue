<template>
  <div class="header">
    <img class="header_logo" src="../assets/logo.png" alt="" />
    <button class="header_burger"><div class="burger_line"></div></button>
  </div>
</template>

<script></script>

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
  border-color: #0e2963;
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
</style>
