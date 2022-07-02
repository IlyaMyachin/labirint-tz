<template>
  <li v-if="window.width >= 768" class="address-delivery__item item-address-delivery" @click="changeStatus">
    <h3 class="item-address-delivery__title">{{ item.delivery }}</h3>
    <span class="item-address-delivery__desc">{{ item.address }}</span>
    <span class="item-address-delivery__price">{{ item.price }}&nbsp;₽</span>
  </li>
  <li v-else class="address-delivery__item item-address-delivery" @click="changeStatus">
    <h3 class="item-address-delivery__title">{{ item.deliveryMobile }}</h3>
    <span class="item-address-delivery__price">{{ item.priceMobile }}&nbsp;₽</span>
    <span class="item-address-delivery__desc">{{ item.addressMobile }}</span>
  </li>
</template>

<script>
export default {
  data() {
    return {
      window: {
        width: 0,
      }
    }
  },
  props: ['item'],
  created() {
    window.addEventListener('resize', this.handleResize);
    this.handleResize();
  },
  methods: {
    handleResize() {
      this.window.width = window.innerWidth;
    },
    changeStatus: function() {
      this.$emit('active', this.item.id)
    }
  },
}
</script>

