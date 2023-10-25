<script setup lang="ts">
import { onMounted, ref } from 'vue';
import Chart from 'chart.js/auto';
import ChartDataLabels from 'chartjs-plugin-datalabels';

const ctx = ref<HTMLCanvasElement>();

onMounted(() => {
  new Chart(ctx.value!, {
    type: 'bar',
    plugins: [ChartDataLabels],
    data: {
      labels: ['Option 1', 'Option 2', 'Option 3'],
      datasets: [
        {
          label: 'Base',
          data: [90, 39, 70],
          borderWidth: 1
        },
        {
          label: 'P50',
          data: [53, 70, 5],
          borderWidth: 1
        },
        {
          label: 'P90',
          data: [73, 25, 100],
          borderWidth: 1
        }
      ],
    },
    options: {
      indexAxis: 'y',
      plugins: {
        title: {
          display: true,
          text: 'Option Costing Summary',
          color: 'black',
          font: {
            size: 24,
          },
          padding: {
            bottom: 10
          }
        }
      }
    }
  });
})
</script>

<template>
  <div class="board-total-cost">
    <canvas ref="ctx" width="700" height="400" />
  </div>
</template>


<style scoped lang="scss">
.board-total-cost {
  padding: 16px;
  border-radius: var(--base-border-radius);
  background-color: var(--white);
}
</style>