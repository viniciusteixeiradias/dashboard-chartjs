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
        'Driver 01',
        'Driver 02',
        'Driver 03'
      ],
      datasets: [{
        label: 'My First Dataset',
        data: [145, 80, 230],
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
          text: 'Key Cost Drivers',
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