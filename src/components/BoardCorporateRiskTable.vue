<script setup lang="ts">
interface Row {
  riskName: string;
  score: 'High' | 'Medium' | 'Low';
  trend: '⬈' | '■' | '⬊';
}

interface ScoreColors {
  high: string;
  medium: string;
  low: string;
}

interface TrendColors {
  '⬈': string; 
  '■': string; 
  '⬊': string;
}

interface Colors {
  score: ScoreColors;
  trend: TrendColors;
}

const rows: Row[] = [
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

const colors: Colors = {
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
        <td :style="`background-color: ${colors.score[(row.score.toLowerCase() as keyof ScoreColors)]};`">{{ row.score }}</td>
        <td :style="`font-weight: 'bold'; color: ${colors.trend[(row.trend.toLowerCase() as keyof TrendColors)]};`">{{ row.trend }}</td>
      </tr>
    </table>
  </div>
</template>

<style scoped lang="scss">
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
</style>