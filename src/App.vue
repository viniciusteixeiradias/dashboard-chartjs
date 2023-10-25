<script setup lang="ts">
import AppBar from './components/AppBar.vue';
import TeamMember from './components/TeamMember.vue';
import BoardTotalCost from './components/BoardTotalCost.vue';
import BoardOptionCostingSummary from './components/BoardOptionCostingSummary.vue';
import BoardCTICommercialInfo from './components/BoardCTICommercialInfo.vue';
import BoardProgressOption from './components/BoardProgressOption.vue';
import BoardProjectSpecificBenchmarking from './components/BoardProjectSpecificBenchmarking.vue';
import BoardKeyCostDrivers from './components/BoardKeyCostDrivers.vue';
import BoardCorporateRiskTable from './components/BoardCorporateRiskTable.vue';
import Timeline from './components/Timeline.vue';

interface Member {
  name: string;
  rule: string;
}

const members: Member[] = [
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
    <BoardCorporateRiskTable />
    <Timeline />
  </div>
</template>

<style scoped lang="scss">
.dashboard {
  margin: 16px;
  display: flex;
  gap: 2rem;
  flex-wrap: wrap;
}
</style>
