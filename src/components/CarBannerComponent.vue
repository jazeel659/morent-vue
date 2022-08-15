<template>
  <div class="ad-banner" :style="{ backgroundColor: backgroundColor }">
    <div class="ad-text-wrapper">
      <h1>{{ title }}</h1>
      <p>{{ subTitle }}</p>
      <button :style="{ backgroundColor: buttonColor }">
        {{ buttonText }}
      </button>
    </div>
    <img :src="imagePath" alt="" />
  </div>
</template>
<script>
export default {
  props: {
    title: String,
    subTitle: String,
    buttonText: {
      type: String,
      default: "Rental Car",
    },
    buttonColor: {
      type: String,
      default: "#3563e9",
    },
    backgroundColor: {
      type: String,
      default: "#5caffc",
    },
    imageName: String,
  },
  computed: {
    imagePath() {
      return import.meta.env.VITE_SUPABASE_STORAGE_BUCKET_URL + this.imageName;
    },
  },
};
</script>
<style scoped lang="scss">
.ad-banner {
  background-color: #5caffc;
  padding: 24px;
  display: flex;
  flex-direction: column;
  border-radius: 10px;
  .ad-text-wrapper {
    max-width: 280px;
    font-family: "Plus Jakarta Sans";
    color: white;
    h1 {
      font-weight: 600;
      font-size: 32px;
      font-style: normal;
      line-height: 120%;
    }

    p {
      font-weight: 500;
      font-size: 16px;
      line-height: 160%;
      margin-top: 16px;
    }
    button {
      background: #3563e9;
      border-radius: 4px;
      padding: 10px 20px;
      margin-top: 20px;
      border: none;
      outline: none;
      color: white;
      font-weight: 600;
      font-size: 16px;
      line-height: 20px;
    }
  }

  img {
    align-self: center;
    @media only screen and (max-width: 768px) {
      width: 270px;
      margin-top: 20px;
    }
  }
}
</style>
