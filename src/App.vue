// App.vue

<template>
  <div id="app">
    <!-- <Values /> -->

    <Introduction />
    <Languages />
    <Education />
    <Projects />
    <Contact />
  </div>
</template>

<script>
import Introduction from "./components/Introduction.vue";
import Languages from "./components/Languages.vue";
import Education from "./components/Education.vue";
import Projects from "./components/Projects.vue";
import Contact from "./components/Contact.vue";

// import Values from "./components/Values.vue";

export default {
  name: "app",
  components: {
    Introduction,
    Languages,
    Education,
    Projects,
    Contact,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Langar&family=Montserrat+Alternates:wght@400;600&family=Montserrat:ital@1&family=Sniglet&display=swap");

body {
  margin: 0px;
}

#app {
  height: 100vh;
  overflow-y: scroll;
  scroll-snap-type: y mandatory;
}

#app .container {
  scroll-snap-align: start;
  padding-bottom: 500px;
}

#app .container:last-of-type {
  padding-bottom: 0px;
}

html {
  overflow: hidden;
}

.background_left {
  position: absolute;
  width: 500px;
  height: 500px;
  left: 288px;
  top: 125px;

  background: rgb(0, 158, 186, 0.7);
}

.background_right {
  /* Text background */

  position: absolute;
  width: 500px;
  height: 500px;
  left: 748px;
  top: 239px;

  background: rgb(0, 158, 186, 0.7);
}

.background_left_alt {
  position: absolute;
  width: 500px;
  height: 500px;
  left: 288px;
  top: 239px;

  background: rgb(0, 158, 186, 0.7);
}

.background_right_alt {
  position: absolute;
  width: 500px;
  height: 500px;
  left: 748px;
  top: 125px;

  background: rgb(0, 158, 186, 0.7);
}

.container {
  position: relative;

  scroll-snap-align: start;
  height: 95vh;
  width: 95vw;

  /* margin-top: calc(100vh / 2 - 864px / 2);

  margin-bottom: calc(100vh / 2 - 864px / 2); */
}

.background {
  /* Background */
  margin: auto;

  position: absolute;
  /* 
  width: 1536px;
  height: 864px; */
  top: 0px;
  background: #005266;

  margin-top: calc(100vh / 2 - 864px / 2);
  margin-bottom: calc(100vh / 2 - 864px / 2);
  margin-left: calc(100vw / 2 - 1536px / 2);
  margin-right: calc(100vw / 2 - 1536px / 2);
}

.line_right {
  /* Top */

  position: absolute;
  width: 400px;
  height: 0px;
  left: 928px;
  top: 75px;

  border-top: 10px solid #a4dcea;
}

.line_left {
  /* Bottom */

  position: absolute;
  width: 400px;
  height: 0px;
  left: 183px;
  top: 789px;

  background: #c4c4c4;
  border-top: 10px solid #a4dcea;
}

.line_right_alt {
  position: absolute;
  width: 400px;
  height: 0px;
  left: 928px;
  top: 789px;

  border-top: 10px solid #a4dcea;
}

.line_left_alt {
  position: absolute;
  width: 400px;
  height: 0px;
  left: 183px;
  top: 75px;

  background: #c4c4c4;
  border-top: 10px solid #a4dcea;
}
</style>
