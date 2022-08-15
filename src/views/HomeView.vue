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
    <div class="card-wrapper">
      <CarCardComponent :isFavorite="true"></CarCardComponent>
      <CarCardComponent :isFavorite="false"></CarCardComponent>
      <CarCardComponent :isFavorite="true"></CarCardComponent>
      <CarCardComponent :isFavorite="true"></CarCardComponent>
    </div>
  </main>
</template>
<script>
import CarBannerComponent from "../components/CarBannerComponent.vue";
import CarCardComponent from "../components/CarCardComponent.vue";
export default {
  components: {
    CarBannerComponent,
    CarCardComponent,
  },
};
</script>
<style scoped lang="scss">
main {
  padding: 32px 64px;
  background-color: #f6f7f9;

  .banners {
    display: flex;
    column-gap: 32px;
    .ad-banner {
      flex: 1;
      &:last-child {
        @media only screen and (max-width: 1200px) {
          display: none;
        }
      }
    }
  }
  .card-wrapper {
    margin-top: 20px;
    display: flex;
    column-gap: 32px;
  }

  @media only screen and (max-width: 768px) {
    padding: 32px 24px;
  }
}
</style>
