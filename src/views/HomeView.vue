<template>
  <main>
    <div class="banners">
      <car-banner-component
        title="The Best Platform for Car Rental"
        subTitle="Ease of doing a car rental safely and reliably. Of course at a low price."
        imageName="koenigsegg-banner.png"
      />
      <car-banner-component
        title="Easy way to rent a car at a low price"
        subTitle="Providing cheap car rental services and safe and comfortable facilities."
        imageName="nissangt-banner.png"
        backgroundColor="#3563E9"
        buttonColor="#5CAFFC"
      />
    </div>
  </main>
</template>
<script>
import CarBannerComponent from "../components/CarBannerComponent.vue";
export default {
  components: {
    CarBannerComponent,
  },
};
</script>
<style scoped>
main {
  padding: 32px 64px;
}
.banners {
  display: flex;
  column-gap: 32px;
}
.banners .ad-banner {
  flex: 1;
}
@media only screen and (max-width: 1200px) {
  .banners .ad-banner:last-child {
    display: none;
  }
}
@media only screen and (max-width: 768px) {
  main {
    padding: 32px 24px;
  }
}
</style>
