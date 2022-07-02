<template>
  <li class="date-delivery__item" @click="changeStatus">
    <h3 v-if="window.width > 1440" class="date-delivery__title">{{ item.date }}</h3>
    <h3 v-else class="date-delivery__title">{{ item.dateMobile }}</h3>
    <span class="date-delivery__desc">{{ item.time }}</span>
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
