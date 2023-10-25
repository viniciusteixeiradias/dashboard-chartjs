<template>
  <div class="app-bar">
    <span>Project Name: Grange Rd</span>
    <span>Region: SA</span>
    <span>Client: DIT</span>
    <span>Project number C&I: 230026</span>
    <span>Project lend: josh@commercialinfrastructure.com.au</span>
    <span>Client representative: John DIT</span>
    <span>Current Milestone: N/A</span>
  </div>
</template>

<style scoped lang="scss">
.app-bar {
  display: flex;
  align-items: center;
  justify-content: space-around;
  height: 60px;
  color: var(--white);
  background-color: var(--color1);
  border-radius: var(--base-border-radius);
  font-size: 14px;

  span {
    display: inline-block;
    text-decoration: none;
    cursor: pointer;

    &::after {
      content: '';
      display: block;
      width: 0;
      height: 1px;
      background-color: var(--white);
      transition: width .3s;
    }

    &:hover::after {
      width: 100%;
    }
  }
}
</style>