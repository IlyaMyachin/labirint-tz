<template>
  <li class="checkbox-block-date-delivery__item">
    <input class="checkbox-block-date-delivery__checkbox" id="check-1" type="checkbox" :checked="item.status" :disabled="item.status">
    <label class="checkbox-block-date-delivery__label" for="check-1">{{ item.option }}</label>
  </li>
</template>

<script>
export default {
  props: ['item']
}
</script>
