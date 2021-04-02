<template>
  <div class="details">
    <!-- <a v-bind:href="link">
      <img src="../assets/icons/Dutch.png" width="30" height="30"
    /></a> -->
    <a v-bind:href="link">
      <img
        :src="require(`../assets/icons/${language.toLowerCase()}.png`)"
        width="30"
        height="30"
      />
    </a>

    <div class="language">
      {{ language }}
      {{ logo }}
    </div>
    <div class="level">
      <div
        class="point"
        v-for="index in parseInt(Math.floor(level / 2))"
        :key="'index' + index.key"
      ></div>
      <div
        class="no-point"
        v-for="index in parseInt(5 - Math.floor(level / 2))"
        :key="'index' + index.key"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Language_detail",
  props: ["language", "level", "logo", "link"],

  methods: {
    getPic(index) {
      return "../assets/" + this.pics[index] + ".png";
    },
  },
  data() {
    return {
      pics: ["dog", "cat", "fish"],
    };
  },
};
</script>

<style>
img {
  margin-top: 10px;
}

.details {
  position: relative;
  top: 132px;
  display: flex;
  width: 400px;

  margin-left: 50px;
}

.icon {
  /* background: url(../icons/dutch.png) center; */
  background-repeat: no-repeat;
  background-size: 50px;

  height: 50px;
  width: 50px;
}

.language {
  width: 70px;
  font-size: larger;
  margin-left: 10px;
  margin-right: 10px;
  line-height: 50px;

  color: #a4dcea;
}

.level {
  display: flex;
}

.point {
  width: 30px;
  height: 30px;
  margin: 10px;

  background: #a4dcea;
  border: 1px solid #000000;
  box-sizing: border-box;
  border-radius: 50px;
}

.no-point {
  width: 30px;
  height: 30px;
  margin: 10px;

  background: rgb(164, 220, 234, 0);
  border: 1px solid #000000;
  box-sizing: border-box;
  border-radius: 50px;
}
</style>
