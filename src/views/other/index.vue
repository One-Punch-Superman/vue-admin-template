<template>
  <div class="container">
    <MdShow v-if="text" :text="text"></MdShow>
  </div>
</template>

<script lang="ts" setup>
import MdShow from '@/components/mdShow/index.vue';
import { getOtherMd } from '@/api/md';

const text = ref('');

onMounted(() => {
  getOtherMd().then((res) => {
    text.value = res.data;
  });
});
</script>

<style lang="scss" scoped>
.container {
  width: 1400px;
  margin: 0 auto;
}
</style>
