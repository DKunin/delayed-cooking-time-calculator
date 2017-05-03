<template>
  <div id="app">
      <div class="icon-holder">
        <svg class="pot" enable-background="new 0 0 128 128" id="Слой_1" version="1.1" viewBox="0 0 128 128" xml:space="preserve" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"><g><path d="M99,113.5H29c-5.5,0-10-4.5-10-10v-65c0-2.8,2.2-5,5-5h80c2.8,0,5,2.2,5,5v65C109,109,104.5,113.5,99,113.5   z" fill="#BEBFCC"/><g opacity="0.5"><path d="M89,97.5c-2.2,0-4-1.8-4-4v-60h8v60C93,95.7,91.2,97.5,89,97.5z" fill="#FFFFFF"/></g><g opacity="0.5"><path d="M99,85.5c-1.1,0-2-0.9-2-2v-50h4v50C101,84.6,100.1,85.5,99,85.5z" fill="#FFFFFF"/></g><path d="M19,103.5L19,103.5c0,5.5,4.5,10,10,10h70c5.5,0,10-4.5,10-10v0H19z" fill="#908F9E"/><path d="M34,103.5v-70H24c-2.8,0-5,2.2-5,5v65c0,5.5,4.5,10,10,10h15C38.5,113.5,34,109,34,103.5z" fill="#FFFFFF"/><path d="M19,29.5V27c0-1.4,1.1-2.5,2.5-2.5h85c1.4,0,2.5,1.1,2.5,2.5v2.5" fill="#A5A4AA"/><path d="M106.5,23H71.8v-1c0-5-4-9-9-9s-9,4-9,9v1H21.5c-2.2,0-4,1.8-4,4s1.8,4,4,4h85c2.2,0,4-1.8,4-4   S108.7,23,106.5,23z M56.8,22c0-3.3,2.7-6,6-6s6,2.7,6,6v1h-12V22z M106.5,28h-85c-0.6,0-1-0.4-1-1s0.4-1,1-1h85c0.6,0,1,0.4,1,1   S107.1,28,106.5,28z" fill="#454B54"/><path d="M124,37h-13.7c-0.7-2.9-3.3-5-6.3-5H24c-3.1,0-5.6,2.1-6.3,5H4c-0.8,0-1.5,0.7-1.5,1.5S3.2,40,4,40h13.5   v63.5c0,6.3,5.2,11.5,11.5,11.5h70c6.3,0,11.5-5.2,11.5-11.5V40H124c0.8,0,1.5-0.7,1.5-1.5S124.8,37,124,37z M107.5,103.5   c0,4.7-3.8,8.5-8.5,8.5H29c-4.2,0-7.6-3-8.4-7h42.1c0.8,0,1.5-0.7,1.5-1.5s-0.7-1.5-1.5-1.5H20.5V38.5c0-1.9,1.6-3.5,3.5-3.5h80   c1.9,0,3.5,1.6,3.5,3.5c0,0,0,0,0,0c0,0,0,0,0,0V103.5z" fill="#454B54"/><circle cx="120" cy="38.5" fill="#AB7866" r="4"/><g><path d="M120,44c-3,0-5.5-2.5-5.5-5.5S117,33,120,33s5.5,2.5,5.5,5.5S123,44,120,44z M120,36    c-1.4,0-2.5,1.1-2.5,2.5s1.1,2.5,2.5,2.5s2.5-1.1,2.5-2.5S121.4,36,120,36z" fill="#454B54"/></g><circle cx="8" cy="38.5" fill="#AB7866" r="4"/><g><path d="M8,44c-3,0-5.5-2.5-5.5-5.5S5,33,8,33s5.5,2.5,5.5,5.5S11,44,8,44z M8,36c-1.4,0-2.5,1.1-2.5,2.5    S6.6,41,8,41s2.5-1.1,2.5-2.5S9.4,36,8,36z" fill="#454B54"/></g></g></svg>
      </div>
      <div class="controls">
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
        HH: '07',
        mm: '00',
      },
      cook: {
        HH: '00',
        mm: '30',
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
      return prettyMs(this.difference);
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
body {
  margin: 0;
}
div {
  text-align: center;
}
.controls {
  padding: 10px 0;
  font-size: 1.4em;
}
.pot {
  width: 100px;
}
.result {
  font-size: 3em;
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
}

h2 {
  text-align: center;
}

</style>
