<template>
  <div class="main__right-block">
    <section class="delivery">
      <div class="delivery__container">
        <h2 class="delivery__title">Доставка</h2>
        <DeliveryAddress />
        <DeliveryDate />
        <DeliveryCheckboxBlock />
      </div>
    </section>
    <section class="recipient">
      <div class="recipient__container">
        <h2 class="recipient__title">Получатель</h2>
        <RecipientInfo />
      </div>
    </section>
  </div>
</template>

<script>
import DeliveryAddress from '@/components/DeliveryAddress.vue';
import DeliveryDate from '@/components/DeliveryDate';
import DeliveryCheckboxBlock from '@/components/DeliveryCheckboxBlock';
import RecipientInfo from '@/components/RecipientInfo.vue';

export default {
  name: 'App',
  components: { DeliveryAddress, DeliveryDate, DeliveryCheckboxBlock, RecipientInfo }
};
</script>
