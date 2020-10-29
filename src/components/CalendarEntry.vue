<template>
<div id="calendar-entry">
<div class="calendar-entry-note">
<input type="text" placeholder="New Event" v-model="inputEntry" required />
<p class="calendar-entry-day">
Day of event: <span class="bold">{{ titleOfActiveDay }}</span>
</p>
<button class="button is-primary is-small is-outlined " style="text-align: center;"
@click="submitEvent(inputEntry)">
Submit
</button>
</div>
<p style="color: red; font-size: 13px" v-if="error">
You must type something first!
</p>
</div>
</template>
<script>
import { store } from './store.js';
export default {
name: 'CalendarEntry',
data () {
return {
inputEntry: '',
error: false
}
},
computed: {
titleOfActiveDay () {
return store.getActiveDay().fullTitle;
}
},
methods: {
submitEvent (eventDetails) {
if (eventDetails === '') return this.error = true;
store.submitEvent(eventDetails);
this.inputEntry = '';
this.error = false;
}
}
}
</script>
<style lang="scss" scoped>
 #calendarentry{
    width: 30%;
    text-align: center;
    height: 300px;
    box-shadow: 0 0 3px 0 rgba(0, 0, 0, .5);
    transform: scale(1);
    transition: transform 0.6s;
}

.calendarentry :hover{
    box-shadow: 0 0 6px 0 rgba(0, 0, 0, .5);
    transform: scale(1.03);
    cursor: pointer;
}

.card i{
    margin: 30px 0 20px 0;
    color: #48b1bf;
    font-size: 50px;
}

#calendar-entry-day p{
    font-weight: 300;
    font-size: 25px;
    margin-bottom: 10px;
}
</style>