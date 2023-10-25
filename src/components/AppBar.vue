<template>
  <div class="app-bar">
    <img height="70" width="150" src="https://commercialinfrastructure.com.au/wp-content/themes/commercialandinfrastructure/assets/img/logo-rev.svg" />
    <span>Project Name: CI - Grange Rd</span>
    <span>Region: SA</span>
    <span>Client: DIT</span>
    <span>Project number C&I: 230026</span>
    <span>Project lend: <a>josh@commercialinfrastructure.com.au</a></span>
    <span>Client representative: John DIT</span>
    <span>Current Milestone: N/A</span>
  </div>
</template>

<style scoped lang="scss">
.app-bar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-inline: 1rem;
  height: 70px;
  color: var(--white);
  background-color: var(--color1);
  border-radius: var(--base-border-radius);
  font-size: 14px;

  span {
    display: inline-block;
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