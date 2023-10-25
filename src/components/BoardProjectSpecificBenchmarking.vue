<script setup lang="ts">
import { onMounted, ref } from 'vue';
import Chart from 'chart.js/auto';
import ChartDataLabels from 'chartjs-plugin-datalabels';

const ctx = ref<HTMLCanvasElement>();

onMounted(() => {
  new Chart(ctx.value!, {
    type: 'bar',
    data: {
      labels: ['Operation 1', 'Operation 2', 'Operation 3', 'Operation 4', 'Operation 5', 'Operation 6'],
      datasets: [{
        label: 'Value of each operation',
        data: [12, 19, 3, 5, 2, 3],
        borderWidth: 1
      }]
    },
    options: {
      scales: {
        y: {
          beginAtZero: true,
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
          text: 'Project Benchmark',
          color: 'black',
          font: {
            size: 24,
          },
          padding: {
            bottom: 10
          }
        }
      }
    },
    plugins: [ChartDataLabels]
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