<template>
  <div class="container">
    <div class="background">
      <div class="background_left_alt">
        <h1>Projects</h1>
        <div class="items_container">
          <div
            v-for="item in cvDataList.projects"
            :key="item"
            class="item_container"
          >
            <div>
              {{ item.title }} at {{ item.year }} using
              {{ item.languages.toString() }} in
              {{ item.tools.toString() }}
            </div>

            <!-- <div v-for="tool in item.tools" :key="tool" class="list_item">
              <div>{{ tool }}</div>
            </div> -->

            <br />
          </div>
        </div>
      </div>
      <div class="line_left_alt"></div>
      <div class="background_right_alt">
        <div class="items_container"></div>
      </div>
      <div class="line_right_alt"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Projects",
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
items_container {
  display: flex;
}

.list_item {
  flex-direction: row;
  width: auto;
}
</style>
