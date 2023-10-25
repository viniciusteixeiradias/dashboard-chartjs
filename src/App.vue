<script setup lang="ts">
import AppBar from './components/AppBar.vue';
import TeamMember from './components/TeamMember.vue';
import BoardTotalCost from './components/BoardTotalCost.vue';
import BoardOptionCostingSummary from './components/BoardOptionCostingSummary.vue';
import BoardCTICommercialInfo from './components/BoardCTICommercialInfo.vue';
import BoardProgressOption from './components/BoardProgressOption.vue';
import BoardProjectSpecificBenchmarking from './components/BoardProjectSpecificBenchmarking.vue';
import BoardKeyCostDrivers from './components/BoardKeyCostDrivers.vue';

const members = [
  {
    name: 'Josh Anfiteatro',
    rule: 'Project Lead'
  },
  {
    name: 'Rashedul Islam',
    rule: 'QS1'
  },
  {
    name: 'Shah Rahman',
    rule: 'QS2'
  }
]

const rows = [
  {
    riskName: 'Regulation and Compilance',
    score: 'High',
    trend: '⬈'
  },
  {
    riskName: 'Cost Cutting',
    score: 'High',
    trend: '■'
  },
  {
    riskName: 'Impact of Currency Volatility',
    score: 'High',
    trend: '⬊'
  },
  {
    riskName: 'Missing Growth Opportunities',
    score: 'High',
    trend: '⬈'
  },
  {
    riskName: 'Inappropriate Systems',
    score: 'High',
    trend: '■'
  },
  {
    riskName: 'Organization Change',
    score: 'Medium',
    trend: '■'
  },
  {
    riskName: 'Emerging Technologies',
    score: 'Medium',
    trend: '⬊'
  },
  {
    riskName: 'Taxation Risk',
    score: 'Medium',
    trend: '⬈'
  },
  {
    riskName: 'Shifting Demographics',
    score: 'Low',
    trend: '■'
  },
  {
    riskName: 'Emerging Markets',
    score: 'Low',
    trend: '⬊'
  }
]

const colors = {
  score: {
    high: '#66C486',
    medium: '#FFD554',
    low: '#F0563E'
  },
  trend: {
    '⬈': '#66C486',
    '■': '#FFD554',
    '⬊': '#F0563E'
  }
}
</script>

<template>
  <AppBar />

  <div class="dashboard">
    <TeamMember v-for="member in members" :member="member" />
    <BoardTotalCost />
    <BoardKeyCostDrivers />
    <BoardOptionCostingSummary />
    <BoardCTICommercialInfo />
    <BoardProgressOption />
    <BoardProjectSpecificBenchmarking />

    <div class="table">
      <span>Corporate Risk</span>
      <table id="customers">
        <tr>
          <th>Risk Name</th>
          <th>Score</th>
          <th>Trend</th>
        </tr>
        <tr v-for="row in rows" :key="row.riskName">
          <td>{{ row.riskName }}</td>
          <td :style="`background-color: ${colors.score[row.score.toLowerCase()]};`">{{ row.score }}</td>
          <td :style="`font-weight: 'bold'; color: ${colors.trend[row.trend.toLowerCase()]};`">{{ row.trend }}</td>
        </tr>
      </table>
    </div>


    <span style="font-size: 24px; font-weight: bold;">Fake Timeline</span>
    <div class="timeline">
        <div class="event">
          <p class="event-date">January 2023</p>
          <p class="event-description">Fake event description for January 2023. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
        <div class="event">
          <p class="event-date">March 2023</p>
          <p class="event-description">Fake event description for March 2023. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
        <div class="event">
          <p class="event-date">June 2023</p>
          <p class="event-description">Fake event description for June 2023. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
        <div class="event">
          <p class="event-date">September 2023</p>
          <p class="event-description">Fake event description for September 2023. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.dashboard {
  margin: 16px;
  display: flex;
  gap: 2rem;
  flex-wrap: wrap;
}

.table {
  width: 500px;
  height: fit-content;
  padding: 16px;
  background-color: var(--white);
  border-radius: var(--base-border-radius);
  display: flex;
  flex-direction: column;
  align-items: center;

  span {
    font-size: 24px;
    font-weight: bold;
    padding-bottom: 16px;
  }

  table {
    width: 100%;
    font-family: Arial, Helvetica, sans-serif;
    border-collapse: collapse;

    td, th {
      border: 1px solid #ddd;
      padding: 6px;
    }

    tr:nth-child(even) {
      background-color: #f2f2f2;
    }

    tr:hover {
      background-color: #ddd;
    }

    th:nth-child(2), td:nth-child(2),
    th:nth-child(3), td:nth-child(3) {
      text-align: center;
    }

    th {
      padding-top: 12px;
      padding-bottom: 12px;
      text-align: left;
      background-color: var(--color1);
      color: white;
    }
  }
}

.timeline {
  width: 100%;
  display: flex;
  flex-direction: row;
  overflow-x: auto;
  white-space: nowrap;
}

.event {
  background-color: #ffffff;
  border: 2px solid #0077b6;
  border-radius: 5px;
  margin: 10px;
  padding: 20px;
  box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.2);
}

.event-date {
  font-weight: bold;
  color: #0077b6;
}

.event-description {
  margin-top: 10px;
  line-break: auto;
}
</style>

