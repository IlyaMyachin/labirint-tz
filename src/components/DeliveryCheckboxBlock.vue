<template>
  <ul class="delivery__checkbox-block checkbox-block-date-delivery">
    <DeliveryCheckboxItemVue v-for="option in optionsList" :key="option.id" :item="option" />
  </ul>
</template>

<script>
import DeliveryCheckboxItemVue from '@/components/DeliveryCheckboxItem'
import options from '@/data/options'

export default {
  data() {
    return {
      optionsList: options
    }
  },
  components: { DeliveryCheckboxItemVue },
}
</script>
