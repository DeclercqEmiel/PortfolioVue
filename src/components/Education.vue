<template>
  <div class="container">
    <div class="background">
      <div class="background_left">
        <h1>Education</h1>
        <div class="items_container">
          <div
            v-for="item in cvDataList.education"
            :key="item"
            class="item_container"
          >
            <div>{{ item.title }} at {{ item.school }}</div>
            <div>{{ item.start_year }} - {{ item.end_year }}</div>
            <br />
          </div>
        </div>
      </div>
      <div class="line_left"></div>
      <div class="background_right">
        <h1>Experience</h1>
        <div class="items_container">
          <div
            v-for="item in cvDataList.experience"
            :key="item"
            class="item_container"
          >
            <div>{{ item.title }} at {{ item.company }}</div>
            <div>{{ item.start_year }} - {{ item.end_year }}</div>
            <div>{{ item.description }}</div>

            <br />
          </div>
        </div>
      </div>
      <div class="line_right"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Education",
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
};
</script>

<style>
.items_container {
  margin-top: 100px;
  text-align: center;
}

.item_container {
  background: rgba(164, 220, 234, 0.9);
  width: 400px;
  margin-left: 50px;
  margin-top: 10px;
}
</style>
