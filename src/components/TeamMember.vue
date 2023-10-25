<script lang="ts" setup>
const props = defineProps<{
  member: { name: string, rule: string }
}>()
</script>

<template>
  <div class="team-member">
    <img src="../assets/default-img.png" />
    <span class="team-member__title">{{ props.member.rule }}</span>
    <span>{{ props.member.name }}</span>
  </div>
</template>

<style lang="scss" scoped>
.team-member {
  height: 200px;
  background-color: white;
  border-radius: var(--base-border-radius);
  width: 150px;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  align-items: center;

  img {
    width: 100%;
    height: 70%;
    border-radius: 5px 5px 0px 0px;
  }

  &__title {
    font-weight: bold;
  }
}
</style>