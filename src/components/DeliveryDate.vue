<template>
  <div class="delivery__date date-delivery">
    <ul class="date-delivery__list">
      <DeliveryDateItem v-for="item in dateList" :key="item.id" :item="item" :class="{ 'is-active': item.active }"
        @active="setActive(item.id)" />
    </ul>
    <a class="date-delivery__link" href="#">Другие дата и&nbsp;время</a>
  </div>
</template>

<script>
import DeliveryDateItem from '@/components/DeliveryDateItem'
import date from '@/data/date'

export default {
  data() {
    return {
      dateList: date
    }
  },
  components: { DeliveryDateItem },
  methods: {
    setActive(id) {
      this.dateList = this.dateList.map((item) => {
        if (item.id === id) {
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
  }
}
</script>
