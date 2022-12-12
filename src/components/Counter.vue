<script lang="ts">
import { useCounterStore } from '../stores/counter';
import type { PropType } from 'vue';
import { defineComponent } from 'vue';

type SexType = 'boy' | 'girl';
export default defineComponent({
  props: {
    sex: {
      type: String as PropType<SexType>,
      required: true,
    },
  },
  setup() {
    const counter = useCounterStore();
    const onAdd = () => {
      counter.count++;
    };
    return {
      counter,
      onAdd,

    };
  },
});
</script>

<template>
  <view>
    <text class="title">
      counter.vue:  {{ counter.count }}
      sex:{{ sex }}
    </text>
    <view class="button" @tap="onAdd">
      ADD
    </view>
  </view>
</template>

<style>
.title {
  font-size: 32px;
}
.button {
  border: 1px solid lightgray;
  padding: 5px 10px;
  width:30%;
  background-color: rgb(11, 222, 120);
  color:#fff;
}
</style>
