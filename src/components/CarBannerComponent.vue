<template>
  <div class="ad-banner">
    <div class="ad-text-wrapper">
      <h1>The Best Platform for Car Rental</h1>
      <p>
        Ease of doing a car rental safely and reliably. Of course at a low
        price.
      </p>
      <button>Rental Car</button>
    </div>
    <img src="@/assets/cars/koenigsegg-banner.png" alt="" />
  </div>
</template>
<script>
</script>
<style scoped>
.ad-banner {
  background-color: #5caffc;
  padding: 24px;
  display: flex;
  flex-direction: column;
}
.ad-text-wrapper {
  font-family: "Plus Jakarta Sans";
  color: white;
}
.ad-text-wrapper h1 {
  font-weight: 600;
  font-size: 32px;
  line-height: 120%;
}
.ad-text-wrapper p {
  font-weight: 500;
  font-size: 16px;
  line-height: 160%;
  margin-top: 16px;
}
.ad-banner .ad-text-wrapper button {
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
.ad-banner img {
  align-self: center;
}
</style>