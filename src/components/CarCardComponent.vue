<template>
  <div class="card-container">
    <div class="title-wrapper">
      <div>
        <h1 class="black-font">{{ carName }}</h1>
        <span>{{ type }}</span>
      </div>

      <Icon class="icon" :icon="favoriteIconStatus" />
    </div>
    <img class="car" :src="imagePath" alt="" />
    <div class="specification-container">
      <div class="specificaion-item">
        <Icon icon="fluent:gas-pump-20-filled" />
        <span>{{ tankCapacity }}L</span>
      </div>
      <div class="specificaion-item">
        <Icon icon="icon-park-outline:steering-wheel" />
        <span>{{ modeToTitleCase }}</span>
      </div>
      <div class="specificaion-item">
        <Icon icon="fluent:people-12-filled" />
        <span>{{ seatingCapacity }} People</span>
      </div>
    </div>
    <div class="price-container">
      <div class="price-wrapper">
        <span class="discounted-price black-font">$99.00/</span>
        <span>day</span>
        <p class="actual-price">$100.00</p>
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
    imageName: String,
    carName: String,
    type: String,
    tankCapacity: Number,
    seatingCapacity: Number,
    mode: String,
  },
  computed: {
    favoriteIconStatus() {
      return this.isFavorite
        ? "ant-design:heart-filled"
        : "ant-design:heart-outlined";
    },
    imagePath() {
      return this.imageName;
    },
    modeToTitleCase() {
      return this.mode.replace(
        /\w\S*/g,
        function (txt) {
          return txt.charAt(0).toUpperCase() + txt.substr(1).toLowerCase();
        }
      );
    }
  },
};
</script>
<style scoped>
.card-container {
  height: 388px;
  min-width: 300px;
  background-color: white;
  padding: 24px;
  border-radius: 10px;
  color: #90a3bf;
  display: flex;
  flex-direction: column;
}

.title-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}

.title-wrapper div {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.title-wrapper div h1 {
  font-size: 20px;
  line-height: 30px;
}

.title-wrapper div span {
  font-size: 14px;
  line-height: 21px;
  font-weight: 600;
}

.title-wrapper .icon {
  color: #ed3f3f;
  font-size: 28px;
}

.specification-container {
  display: flex;
  position: static;
  margin-top: 37px;
  column-gap: 15px;
  color: #90a3bf;
}

.specificaion-item {
  display: flex;
  align-items: center;
  column-gap: 4px;
}

.specification-container span {
  font-family: "Plus Jakarta Sans";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 18px;
  color: #90a3bf;
}

.price-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 24px;
}


.price-wrapper div:first-child {
  display: flex;
  font-weight: bold;
}

button {
  border: none;
  background-color: #3563e9;
  border-radius: 4px;
  padding: 10px 20px;
  color: white;
  font-weight: 600;
}

.car {
  margin-top: 64px;
  height: 72px;
  align-self: center;
}

.black-font {
  color: black;
  font-weight: bold;
}

.actual-price {
  text-decoration: line-through;
}
</style>
