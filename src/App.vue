<template>
  <main class="wrapper">
    <div class="container">
      <div class="row">
        <shopping class="col--big"></shopping>
        <stats class="col--small"></stats>
      </div>
    </div>
  </main>
</template>

<script>
import Stats from "./components/Stats";
import RecentShopping from "./components/RecentShopping";

export default {
  name: "app",
  components: {
    stats: Stats,
    shopping: RecentShopping
  }
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: #002ac1;
}

.wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

.container {
  max-width: 1400px;
  width: 100vw;
  margin: 0 auto;
  padding: 1rem;
}

.row {
  display: flex;
}

.col--big {
  flex: 3;
  margin-right: 0.5rem;
}

.col--small {
  flex: 1;
  flex-shrink: 1;
  margin-left: 0.5rem;
}

.card {
  background: #fff;
  border-radius: 14px;
}

.icon {
  width: 20px;
  height: 30px;
  display: inline-block;
  margin-right: 1rem;
  object-fit: contain;
}
</style>
