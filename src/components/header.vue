<template>
  <div class="container">
    <div class="row">
      <div class="col-md-6">
        <div class="logo">
          <img :src="imgSrc" alt="logo" />
        </div>
      </div>
      <div class="col-md-6">
        <div class="right-nav">
          <div class="container">
            <div class="row">
              <div class="col-md-7">
                <div class="log">
                  <p class="name">Welcome Hikigaya Hachiman</p>
                  <p class="log">Last Seen 21/5/2019 15:52:26</p>
                </div>
              </div>
              <div class="col-md-5">
                <div class="menu_icons">
                  <i class="fa fa-envelope" aria-hidden="true"></i>
                  <i class="fa fa-bell" aria-hidden="true"></i>
                  <i class="fa fa-power-off" aria-hidden="true"></i>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      imgSrc: require("../assets/img/logo2.png")
    };
  }
};
//linear-gradient(60deg,#ffa726,#fb8c00);
</script>

<style>
nav {
  width: 100%;
  height: 70px;
  background: #e4e2e2;
}
.logo {
  position: relative;
  top: 11px;
  left: 9px;
  width: 150px;
  height: 65;
  display: inline-block;
  color: #646464;
}
.right-nav {
  padding: 12px;
}
.log {
  position: relative;
  top: 18px;
  padding: 0;
  margin: 0;
  line-height: 0;

  font-weight: 500;
  color: rgb(93, 137, 168);
  float: right;
}
.log p {
  padding: 0;
  margin: 0;
  font-weight: 300;
}
.menu_icons {
  position: relative;
  top: 17px;
}
.menu_icons i {
  width: 24px;
  height: 24px;
  color: rgb(93, 137, 168);
}
</style>
