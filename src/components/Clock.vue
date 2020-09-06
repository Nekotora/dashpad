<template>
  <div class="module-click">
    <transition name="clock">
      <div class="clock-item">
        {{time.hours}}:{{time.minutes}}:{{time.seconds}}
      </div>
    </transition>
  </div>
</template>

<script>
import moment from 'moment';
export default {
  name: 'Clock',
  props: {
  },
  data() {
    return {
      time: {
        hours: '--',
        minutes: '--',
        seconds: '--'
      },
      looper: null
    }
  },
  mounted() {
    if(!this.looper){
      this.looper = setInterval(() => {
        this.updateClock();
      }, 1000)
    }
  },
  methods: {
    updateClock() {
      this.time = {
        hours: moment().format('HH'),
        minutes: moment().format('mm'),
        seconds: moment().format('ss')
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.clock-item{
  font-size: 50px;
}
.clock-enter-active {
  animation: clock-in .5s;
}
.clock-leave-active {
  animation: clock-in .5s reverse;
}
@keyframes clock-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
</style>
