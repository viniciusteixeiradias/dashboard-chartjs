<script setup lang="ts">
import { onMounted, ref } from 'vue';
import Chart from 'chart.js/auto';

const ctx = ref<HTMLCanvasElement>();

onMounted(() => {
  const labels = [0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100].map(v => `${v}%`);
  const p1Data = [0, 15, 40, 70, 40, 80, 40, 70, 40, 70, 100];
  const p2Data = [0, 20, 50, 80, 50, 60, 25, 80, 50, 80, 100];
  const p3Data = [0, 21, 20, 40, 20, 70, 30, 40, 20, 40, 100];
  
  new Chart(ctx.value!, {
    type: 'line',
    data: {
      labels: labels,
      datasets: [{
        label: 'Base',
        data: p1Data,
        fill: false
      }, {
        label: 'P50',
        data: p2Data,
        fill: false
      }, {
        label: 'P90',
        data: p3Data,
        fill: false
      }]
    },
    options: {
      scales: {
        y: {
          ticks: {
            callback: (value: number | string) => `${value}%`
          }
        }
      },
      plugins: {
        title: {
          display: true,
          text: 'Progress Option',
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