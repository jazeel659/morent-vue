<template>
  <main>
    <div class="banners">
      <car-banner-component title="The Best Platform for Car Rental"
        subTitle="Ease of doing a car rental safely and reliably. Of course at a low price."
        imageName="banners/koenigsegg-banner.png" />
      <car-banner-component title="Easy way to rent a car at a low price"
        subTitle="Providing cheap car rental services and safe and comfortable facilities."
        imageName="banners/nissangt-banner.png" backgroundColor="#3563E9" buttonColor="#5CAFFC" />
    </div>
    <div class="selection-wrapper">
      <SelectorComponent label="Pick - Up" />
      <button class="switch">
        <Icon icon="octicon:arrow-switch-24" color="white" height="24" width="24" :rotate="1" />
      </button>
      <SelectorComponent label="Drop - Off" />
    </div>
    <div class="card-wrapper">
      <car-card-component v-for="car in cars" :is-favorite="true" :image-name="car.img_url" :car-name="car.name"
        :type="car.type" :key="car.id" :seating-capacity="car.seating_capacity" :tank-capacity="car.tank_capacity"
        :mode=car.mode />
    </div>
  </main>
</template>
<script>
import CarBannerComponent from "../components/CarBannerComponent.vue";
import CarCardComponent from "../components/CarCardComponent.vue";
import supabase from '../supabase';
import SelectorComponent from "../components/SelectorComponent.vue";
import { Icon } from '@iconify/vue';
export default {
  components: {
    CarBannerComponent,
    CarCardComponent,
    SelectorComponent,
    Icon
  },
  data() {
    return {
      cars: [],
    };
  },
  async created() {
    const carModels = await supabase.from('cars_models').select()
    console.log(carModels.data)
    this.cars = carModels.data
  }
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

  .selection-wrapper {
    display: flex;
    justify-content: space-between;
    column-gap: 44px;
    align-items: center;
    margin-top: 32px;

    .selector-wrapper {
      flex: 1;
    }

    button.switch {
      width: 60px;
      height: 60px;


      background: #3563E9;
      border-radius: 10px;
      border: none;
      outline: none;
    }
  }

  .card-wrapper {
    margin-top: 20px;
    display: flex;
    column-gap: 32px;
    overflow: auto;
    padding-bottom: 15px;
  }

  @media only screen and (max-width: 768px) {
    padding: 32px 24px;
  }
}

::-webkit-scrollbar {
  width: 10px;
  height: 10px;
}

::-webkit-scrollbar-track {
  border-radius: 10px;
  background-color: rgba(255, 255, 255, 0.1);
}

::-webkit-scrollbar-thumb {
  background-color: #5caffc9f;
  border-radius: 10px;
  -webkit-box-shadow: rgba(0, 0, 0, 0.12) 0 3px 13px 1px;
}
</style>
