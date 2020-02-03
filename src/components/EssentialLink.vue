<template>
  <q-item clickable tag="a" target="_blank" :href="link">
    <q-item-section v-if="icon" avatar>
      <q-icon :name="icon" />
    </q-item-section>

    <q-item-section>
      <q-item-label>{{ title }}</q-item-label>
      <q-item-label caption>{{ caption }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script lang="ts">
import Vue from 'vue'
import Component from 'vue-class-component';
import { Prop } from 'vue-property-decorator';

@Component
export default class EssentialLink extends Vue {
  @Prop({required: true}) readonly title: string | undefined
  @Prop({required: true}) readonly caption: string | undefined
  @Prop({required: true}) readonly link: string | undefined
  @Prop({required: true}) readonly icon: string | undefined
}
// export default Vue.extend({
//   name: 'EssentialLink',
//   props: {
//     title: {
//       type: String,
//       required: true,
//     },
//
//     caption: {
//       type: String,
//       default: '',
//     },
//
//     link: {
//       type: String,
//       default: '#',
//     },
//
//     icon: {
//       type: String,
//       default: '',
//     },
//   },
// });
</script>
