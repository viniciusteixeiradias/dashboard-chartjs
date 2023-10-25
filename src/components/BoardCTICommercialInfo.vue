<script lang="ts" setup>
import { onMounted, ref } from 'vue';
import Chart from 'chart.js/auto';
import ChartDataLabels from 'chartjs-plugin-datalabels';

const ctx = ref<HTMLCanvasElement>();

onMounted(() => {

  new Chart(ctx.value!, {
    type: 'doughnut',
    data: {
      labels: [
        'Contract Amount',
        'Accural',
        'Remaining Contract Amount'
      ],
      datasets: [{
        label: 'My First Dataset',
        data: [300, 50, 100],
        hoverOffset: 4,
        borderWidth: 1
      }]
    },
    plugins: [ChartDataLabels],
    options: {
      plugins: {
        datalabels: {
          font: {
            size: 14,
          },
          color: 'white',
          formatter: function(value) {
            return `A$ ${value}k`;
          }
        },
        title: {
          display: true,
          text: 'CTI Commercial Information',
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
  })
})
</script>

<template>
  <div class="board-cti-commercial-info">
    <canvas ref="ctx" width="350" height="400"></canvas>
  </div>
</template>

<style lang="scss" scoped>
.board-cti-commercial-info {
  padding: 16px;
  border-radius: var(--base-border-radius);
  background-color: var(--white);
  height: 400px;
}
</style>