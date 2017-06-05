<template>
  <div id="app">
      <div class="controls now">
        Now: {{processDate(new Date(), 'HH:mm')}}
      </div>
      <div class="controls">
        Ready by: <vue-timepicker v-model="time" :minute-interval="5"></vue-timepicker>
      </div>
      <div class="controls">
        Cook for: <vue-timepicker v-model="cook" :minute-interval="5"></vue-timepicker>
      </div>
      <div class="controls result">
        <div v-if="difference > 0">{{delay}}</div>
        <div v-if="difference < 0">
          <svg width="80%" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 302.484 404.519" overflow="visible"><g fill="none"><path d="M302.484 404.519h-2v-2.272h2v2.272z"/><path d="M76.938 198.246l82-143M158.938 55.246l117.5 197.5M276.438 252.746l14.5-27M290.938 225.746l-132-223.5M46.938 199.246l112-197M126.438 1.246h32.5M.438 226.246l127.5-226M.438 226.246h229M229.438 226.246l-85.5-145M.438 226.246l14.5 26.5M14.938 252.746h261.5M212.938 199.246h-166M11.358 333.949h205.925M11.358 314.412h215.676M227.034 314.412l74.42 68.675M301.454 383.086v20.278M301.454 403.365H40.368M41.552 383.086h259.902M11.358 333.949h205.749M25.567 368.878h226.749M25.567 349.341h191.818M217.385 349.341l19.537 18.944M217.385 349.341V334.54M216.912 333.843l35.403 35.035M31.105 359.246c0-5.522-2.687-10-6-10s-6 4.478-6 10 2.687 10 6 10 6-4.478 6-10zM47.771 393.246c0-5.522-2.687-10-6-10s-6 4.478-6 10 2.687 10 6 10 6-4.478 6-10zM17.438 324.246c0-5.522-2.687-10-6-10s-6 4.478-6 10 2.687 10 6 10 6-4.478 6-10z" stroke="#000"/></g></svg>
        </div>
      </div>
  </div>
</template>

<script>
import fecha from 'fecha';
import VueTimepicker from 'vue2-timepicker';
import prettyMs from 'pretty-ms';

export default {
  name: 'app',
  components: {
    VueTimepicker,
  },
  data() {
    return {
      time: {
        HH: '06',
        mm: '15',
      },
      cook: {
        HH: '00',
        mm: '40',
      },
    };
  },
  computed: {
    difference() {
      const now = fecha.format(Date.now(), 'HH:mm:YYYY:MM:DD').split(':');
      const tH = parseInt(this.time.HH, 10);
      const tM = parseInt(this.time.mm, 10);
      const cH = parseInt(this.cook.HH, 10);
      const cM = parseInt(this.cook.mm, 10);
      const cookToMs = (cH * 60 * 60 * 1000) + (cM * 60 * 1000);
      const later = (
        (tH + cH) <
        parseInt(now[0], 10)
      );
      let finishDate = new Date(
        now[2],
        now[3] - 1,
        now[4],
        tH,
        tM);
      if (later) {
        finishDate = new Date(finishDate.getTime() + (1000 * 60 * 60 * 24));
      }
      return finishDate.getTime() - Date.now() - cookToMs;
    },
    delay() {
      return prettyMs(this.difference).replace(/\s(\d|\.)+s/, '');
    },
  },
  methods: {
    processDate(date, string) {
      return fecha.format(date, string);
    },
  },
};

</script>

<style>
body, html, #app {
  height: 100%;
}

body {
  margin: 0;
}

div {
  text-align: center;
}
.controls {
  padding: 10px 0;
  font-size: 2em;
}
.pot {
  width: 100px;
}
.now {
  font-size: 3em;
}

.result {
  font-size: 4em;
  white-space: nowrap;
}

.icon-holder {
  text-align: center;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background-color: #bdc3c7;
}

</style>
