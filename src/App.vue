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
  background: linear-gradient(to bottom, #002ac1 40%, #fff 2%);
  font-family: "Nunito Sans", sans-serif;
  @media screen and (max-width: 968px) {
    background: #002ac1;
  }
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
  @media screen and (max-width: 968px) {
    display: block;
  }
}

.col--big {
  flex: 3;
  @media screen and (min-width: 968px) {
    margin-right: 0.5rem;
  }
  @media screen and (max-width: 968px) {
    margin-bottom: 2rem;
  }
}

.col--small {
  flex: 1;
  flex-shrink: 1;
  @media screen and (min-width: 968px) {
    margin-left: 0.5rem;
  }
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
