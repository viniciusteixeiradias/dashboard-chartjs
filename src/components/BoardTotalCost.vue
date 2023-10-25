<script setup lang="ts">
import { onMounted, ref } from 'vue';
import Chart from 'chart.js/auto';
import ChartDataLabels from 'chartjs-plugin-datalabels';

const ctx = ref<HTMLCanvasElement>();

onMounted(() => {
  new Chart(ctx.value!, {
    type: 'bar',
    data: {
      labels: ['Current Cost'],
      datasets: [
        {
          label: 'Base',
          data: [90],
          borderWidth: 1
        },
        {
          label: 'P50',
          data: [53],
          borderWidth: 1
        },
        {
          label: 'P90',
          data: [73],
          borderWidth: 1
        }
      ]
    },
    plugins: [ChartDataLabels],
    options: {
      scales: {
        y: {
          beginAtZero: true,
          max: 100,
          ticks: {
            callback: (value: number | string) => `${value}k`
          }
        }
      },
      plugins: {
        datalabels: {
          formatter: function(value) {
            return `A$ ${value}k`;
          }
        },
        title: {
          display: true,
          text: 'Total Project Cost',
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
  height: fit-content;
}
</style>