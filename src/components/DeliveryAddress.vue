<template>
  <div class="delivery__address address-delivery">
    <div class="address-delivery__buttons-block">
      <button class="address-delivery__button" :class="{ 'is-disabled': currentActive === 1 }"  @click="setActive(currentActive - 1)">
        <svg width="40" height="40" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
          <rect x="0.5" y="0.5" width="39" height="39" rx="3.5" fill="white" />
          <path d="M16.0463 20L24.2963 28.25L21.9397 30.6066L11.333 20L21.9397 9.39331L24.2963 11.75L16.0463 20Z"
            fill="#333333" />
          <rect x="0.5" y="0.5" width="39" height="39" rx="3.5" stroke="#D6D6D6" />
        </svg>
      </button>
      <button class="address-delivery__button" :class="{ 'is-disabled': currentActive === (addressList.length) }" @click="setActive(currentActive + 1)">
        <svg width="40" height="40" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
          <rect x="0.5" y="0.5" width="39" height="39" rx="3.5" fill="white" />
          <path d="M23.5835 20L15.3335 28.25L17.6902 30.6066L28.2969 20L17.6902 9.39331L15.3335 11.75L23.5835 20Z"
            fill="#333333" />
          <rect x="0.5" y="0.5" width="39" height="39" rx="3.5" stroke="#D6D6D6" />
        </svg>
      </button>
    </div>
    <ul class="address-delivery__list">
      <DeliveryAddressItemVue v-for="item in addressList" :key="item.id" :item="item"
        :class="{ 'is-active': item.active }" @active="setActive(item.id)" />
    </ul>
    <a class="address-delivery__link" href="#">Выбрать новое место и способ</a>
  </div>
</template>

<script>
import DeliveryAddressItemVue from '@/components/DeliveryAddressItem'
import address from '@/data/address'

export default {
  data() {
    return {
      addressList: address,
      currentActive: 1,
    }
  },
  components: { DeliveryAddressItemVue },
  methods: {
    setActive(id) {
      this.addressList = this.addressList.map((item) => {
        if (item.id === id) {
          this.currentActive = item.id
          return {
            ...item,
            active: true
          }
        } else {
          return {
            ...item,
            active: false
          }
        }
      });
    }
  },
  computed: {
    checkActive() {
      return this.addressList
    }
  }
}
</script>

