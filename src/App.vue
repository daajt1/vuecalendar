<template>
  <div id="app">
    <CalendarWeek />
    <CalendarEntry />
    <NumberDisplay />
  </div>
</template>

<script>
import NumberDisplay from "./components/NumberDisplay";
import CalendarWeek from "./components/CalendarWeek";
import CalendarEntry from "./components/CalendarEntry";

export default {
  name: "App",
  components: {
    NumberDisplay,
    CalendarWeek,
    CalendarEntry,
  },
};
</script>

<style lang="scss">
#app {
height: inherit;
background: #6e6e6e;
display: flex;
flex-direction: column;
align-items: center;
-webkit-align-items: center;
justify-content: center;
-webkit-justify-content: center;
}


</style>
