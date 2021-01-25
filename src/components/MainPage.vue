<template>
  <div>
    <h1>{{ currentTime }}</h1>    
    <h1>{{ currentCopenhagenTime }}</h1>
  </div>
</template>

<script lang="ts">
import { Vue } from 'vue-class-component';

import dayjs from 'dayjs';
import timeZone from "dayjs/plugin/timezone";
import isoWeek from "dayjs/plugin/isoWeek";
dayjs.extend(timeZone);
dayjs.extend(isoWeek);

export default class MainPage extends Vue {
  // This one works well
  get currentTime(){
    return dayjs();
  }
  // This one causes an error
  get currentCopenhagenTime(){
    return dayjs().tz("Europe/Copenhagen");
  }
}
</script>