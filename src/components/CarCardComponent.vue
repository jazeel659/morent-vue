<template>
  <div class="card-container">
    <div class="title-wrapper">
      <div>
        <h1>Koenigsegg</h1>
        <span>Sport</span>
      </div>

      <Icon class="icon" :icon="favoriteIconStatus" />
    </div>
    <img class="car" src="../assets/cars/koenigsegg.png" alt="" />
    <div class="specification-container">
      <div class="mileage">
        <Icon icon="fluent:gas-pump-20-filled" />
        <span>90L</span>
      </div>
      <div class="mode">
        <Icon icon="icon-park-outline:steering-wheel" />
        <span>Manual</span>
      </div>
      <div class="capacity">
        <Icon icon="fluent:people-12-filled" />
        <span> 2 People</span>
      </div>
    </div>
    <div class="price-container">
      <div class="price-wrapper">
        <p class="discounted-price">$99.00/<span>day</span></p>
        <p class="actual-price">$100.00/</p>
      </div>
      <button>Rent Now</button>
    </div>
  </div>
</template>
<script>
import { Icon } from "@iconify/vue";
export default {
  components: {
    Icon,
  },
  props: {
    isFavorite: {
      type: Boolean,
      default: false,
    },
  },
  computed: {
    favoriteIconStatus() {
      return this.isFavorite
        ? "ant-design:heart-filled"
        : "ant-design:heart-outlined";
    },
  },
};
</script>
<style scoped>
.card-container {
  height: 388px;
  background-color: white;
  padding: 24px;
  border-radius: 10px;
}

.title-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
icon {
  font-size: 15px;
}
.title-wrapper div {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.title-wrapper div h1 {
  size: 20px;
  line-height: 30px;
}
.title-wrapper div span {
  size: 14px;
  line-height: 21px;
}
.mileage {
  display: flex;
  align-items: center;
  column-gap: 8px;
}
.specification-container {
  display: flex;
  position: static;
  margin-top: 37px;
  column-gap: 15px;
  color: #90a3bf;
}
.specification-container span {
  font-family: "Plus Jakarta Sans";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 18px;
  color: #90a3bf;
}
.capacity {
  display: flex;
  align-items: center;
  column-gap: 8px;
}
.mode {
  display: flex;
  align-items: center;
  column-gap: 8px;
}

.persons {
  display: flex;
  align-items: center;
  grid-column-gap: 8px;
}
.price-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 24px;
}
.price-wrapper {
}
.price-wrapper div:first-child {
  display: flex;
}
button {
  border: none;
  background-color: #3563e9;
  border-radius: 4px;
  padding: 10px 20px;
  color: white;
  width: 100px;
}
.car {
  margin-top: 64px;
}
.normal {
}
</style>
