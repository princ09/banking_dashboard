<template>
  <div>
    <nav>
      <app-header></app-header>
    </nav>
    <main>
      <div class="container-fluid" style="margin-left: 0; padding-lift:0;">
        <div class="row">
          <app-left></app-left>
          <app-right></app-right>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
import Header from "./components/header.vue";
import Left from "./components/Left.vue";
import Right from "./components/right.vue";
export default {
  name: "App",
  components: {
    "app-header": Header,
    "app-left": Left,
    "app-right": Right
  }
};
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
body {
  background-color: white;
  color: black;
  font-weight: 300;
}
main {
  padding: 10px;
}
</style>
