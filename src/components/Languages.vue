<!-- <div>
    <h1>Languages</h1>
    <ul>
      <li v-for="item in cvDataList.languages" :key="item">
        {{ item.language }}: {{ item.level }}
      </li>
    </ul>
  </div> -->
<template>
  <div class="container">
    <div class="background">
      <div class="background_left_alt">
        <div>
          <h1>Languages</h1>
          <Language_detail
            v-for="(item, index) in cvDataList.languages"
            :key="index"
            v-bind:language="item.language"
            v-bind:level="item.level"
            v-bind:image="item.logo"
            v-bind:link="item.link"
          ></Language_detail>
          <!-- <li v-for="item in cvDataList.languages" :key="item">
        {{item}}
            <Language_detail language="{{item}}" />
          </li> -->
          <!-- <Language_detail />
          <Language_detail />
          <Language_detail />
          <Language_detail /> -->
        </div>
      </div>
      <div class="line_left_alt"></div>
      <div class="background_right_alt">
        <h1>Programming languages and frameworks</h1>
        <Language_detail
          v-for="item in cvDataList.programming_languages
            .sort((t1, t2) => (t1.level < t2.level ? 1 : -1))
            .slice(0, 5)"
          v-bind:key="item.language"
          v-bind:language="item.language"
          v-bind:level="item.level"
          v-bind:image="item.logo"
          v-bind:link="item.link"
        ></Language_detail>
      </div>
      <div class="line_right_alt"></div>
    </div>
  </div>
</template>

<script>
import Language_detail from "./Language_detail.vue";

export default {
  name: "Languages",
  data() {
    return {
      cvDataList: [],
    };
  },
  methods: {
    getCVData() {
      fetch("cv_data.json")
        .then((response) => response.json())
        .then((data) => (this.cvDataList = data));
    },
  },
  beforeMount() {
    this.getCVData();
  },
  components: {
    Language_detail,
  },
};
</script>

<style>
h1 {
  /* Languages */
  top: 0px;

  margin-top: 40px;
  position: absolute;
  width: 80%;
  left: 10%;

  font-family: Roboto;
  font-style: normal;
  font-weight: normal;
  font-size: 25px;
  line-height: 35px;
  text-align: center;

  color: #a4dcea;

  border-bottom: #a4dcea 3px solid;
}

.thin_line_top {
  /* Top languages */

  position: absolute;
  width: 400px;
  height: 10px;

  border-top: 3px solid #a4dcea;
}
</style>
