<template>
  <div class="card-container">
    <div class="title-wrapper">
      <h1>Koenigsegg</h1>
      <span>Sport</span>
      <Icon :icon="favoriteIconStatus" />
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
}
.mileage {
  display: flex;
  align-items: center;
  column-gap: 8px;
}
.specification-container {
  display: flex;
  position: absolute;
  top: 180px;
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
.persons {
  display: flex;
  align-items: center;
  column-gap: 8px;
}
.mode {
  display: flex;
  align-items: center;
}
.cir {
  display: flex;
  position: relative;
  align-items: center;
  width: 22px;
}
.mode .cir-1 {
  width: 20px;
  height: 20px;
  background-color: white;
  border-radius: 10px;
  position: absolute;
  left: 1px;
}
.mode .cir-2 {
  width: 16px;
  height: 16px;
  background-color: #90a3bf;
  border-radius: 8px;
  position: absolute;
  left: 2px;
}
.mode .cir-3 {
  width: 12px;
  height: 12px;
  background-color: white;
  border-radius: 6px;
  position: absolute;
  left: 4px;
}
.mode .cir-4 {
  width: 8px;
  height: 8px;
  background-color: #90a3bf;
  border-radius: 4px;
  position: absolute;
  left: 6px;
}
.rec1 {
  width: 4px;
  height: 2px;
  background-color: #90a3bf;
  position: absolute;
  left: 3px;
}
.rec2 {
  width: 2px;
  height: 4px;
  background-color: #90a3bf;
  align-self: flex-end;
  position: absolute;
  top: 15px;
  left: 9.5px;
}
.rec3 {
  width: 4px;
  height: 2px;
  background-color: #90a3bf;
  position: absolute;
  left: 13px;
}
.persons {
  display: flex;
}
.price-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: relative;
  top: 160px;
  width: 245px;
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
  position: absolute;
  right: 20px;
}
.car {
  position: absolute;
}
.normal {
}
</style>
