<template>
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
</template>

<style scoped lang="scss">
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