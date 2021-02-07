<template>
  <div>
    <div class="progress">
      <div
        class="progress-bar bg-info"
        role="progressbar"
        :style="{ width: barWidth + '%' }"
        aria-valuenow="50"
        aria-valuemin="0"
        aria-valuemax="100"
      >
        {{ currentItemCount }} /10
      </div>
    </div>
  </div>
</template>

<script>
import { eventBus } from "../main";
export default {
  data() {
    return {
      currentItemCount: 0,
      barWidth: 0,
    };
  },
  created() {
    eventBus.$on("progress", (progress) => {
      this.currentItemCount = progress;
      this.barWidth = this.currentItemCount * 10;
    });
  },
};
</script>

<style>
</style>