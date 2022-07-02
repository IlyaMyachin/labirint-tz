<template>
  <ul class="recipient__list">
    <li class="recipient__item">
      <label v-if="window.width >= 768" class="recipient__label" for="fullname">Имя и фамилия</label>
      <label v-else class="recipient__label" for="fullname">Имя и фамилия, как в паспорте</label>
      <select class="recipient__select custom-select" name="full-name" id="fullname">
        <option v-if="window.width >= 768" selected>Вольфганг Вениаминович Константинопольский</option>
        <option v-else>Константин Константинопольский</option>
      </select>
      <a class="recipient__button recipient__button--client" href="# ">Новый получатель</a>
    </li>
    <li class="recipient__item">
      <label v-if="window.width >= 768" class="recipient__label" for="phone">Контактный телефон</label>
      <label v-else class="recipient__label" for="fullname">Мобильный телефон</label>
      <select class="recipient__select custom-select" name="full-name" id="phone">
        <option v-if="window.width >= 768" selected>+7 910 234-56-78</option>
        <option v-else>+7 901 234-56-78</option>
      </select>
      <a class="recipient__button  recipient__button--phone" href="#">Новый телефон</a>
    </li>
  </ul>
</template>>

<script>
export default {
    data() {
    return {
      window: {
        width: 0,
      }
    }
  },
  created() {
    window.addEventListener('resize', this.handleResize);
    this.handleResize();
  },
  methods: {
    handleResize() {
      this.window.width = window.innerWidth;
    }
  }
}
</script>
