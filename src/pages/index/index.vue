<script lang="ts">
import './index.scss';
import Counter from '../../components/Counter.vue';
import { useCounterStore } from '../../stores/counter';
import { computed, defineComponent } from 'vue';

export default defineComponent({
  name: 'Index',
  components: {
    Counter,
  },
  setup() {
    const countStore = useCounterStore();
    const val = computed(() => countStore.count);
    return {
      val,
    };
  },
});
</script>

<template>
  <view class="index">
    <Counter sex="boy" />
    <view>
      index.vue: {{ val }},
    </view>
  </view>
</template>
