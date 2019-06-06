<template>
  <div class="filter">
    <img class="icon" src="../assets/icons/filter.png" alt="filter">
    <p class="filter__text">Filter</p>
    <button class="filter__button">
      <img src="../assets/arrow.png" alt="strzałka w dół">
    </button>
  </div>
</template>

<script>
export default {
  name: "shopFilter"
};
</script>

<style lang="scss">
.filter {
  display: flex;
  align-items: center;
  margin-left: auto;
}

.filter__text {
  font-size: 14px;
  color: #1d2329;
}

.filter__button {
  cursor: pointer;
  margin-left: 1rem;
  background: none;
  border: none;
  transition: 200ms;
}
</style>
