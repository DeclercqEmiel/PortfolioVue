<template>
  <div class="container">
    <div class="background">
      <div class="background_left_alt">
        <h1 id="contact">Contact</h1>
        <div class="contact_wrap">
          <div class="contact">
            <div>Country: {{ cvDataList.contact.country }}</div>
            <div>City: {{ cvDataList.contact.city }}</div>
            <div>Telephone: {{ cvDataList.contact.telephone }}</div>
            <div>Email: {{ cvDataList.contact.email }}</div>
          </div>
        </div>
      </div>

      <div class="line_left_alt"></div>
      <div class="background_right_alt">
        <div class="items_container">
          <a href="https://github.com/DeclercqEmiel">
            <img
              :src="require(`../assets/icons/github.png`)"
              width="50"
              height="50"
            />
          </a>
          <a href="https://www.linkedin.com/in/emieldeclercq/">
            <img
              :src="require(`../assets/icons/linkedin.png`)"
              width="50"
              height="50"
            />
          </a>
        </div>
      </div>
      <div class="line_right_alt"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Contact",
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
.intern {
  -webkit-animation: in 1s;
}

.intern:hover {
  -webkit-animation: out 1s;
}

@-webkit-keyframes in {
  from {
    -webkit-transform: rotate(0deg);
  }
  to {
    -webkit-transform: rotate(360deg);
  }
}

@-webkit-keyframes out {
  0% {
    -webkit-transform: rotate(360deg);
  }
  100% {
    -webkit-transform: rotate(0deg);
  }
}

.test {
  font-size: 2em;
  color: red;
  animation: testout 1s;
}

.test:hover {
  color: blue;
  animation: testin 1s forwards;
}

.contact {
  padding: 0px;
  background-color: white;
  /* opacity: 0.8; */
  border: #a4dcea 7px solid;
  border-radius: 20px;
  padding: 10px;
  color: #005266;
  margin: 30px;
  transform: perspective(1000px) rotateX(90deg) translateY(-50px);
  -webkit-animation: fallin 0.75s;
}

.placeholder_title {
  color: #005266;
  transform: perspective(1000px) rotateX(30deg) translateY(30px) rotate(10deg)
    skew(-60deg);
  margin: 0px;
  font-weight: 800;
}

.contact_wrap {
  left: 50px;
  margin: auto;
  margin-top: 150px;
  width: 400px;
  height: 300px;
  background: url("../assets/stack.png");
  background-size: 400px 300px;
  position: absolute;
  z-index: 999;
}

.contact_wrap:hover .contact {
  border: #a4dcea 7px solid;
  -webkit-animation: fallout 1s;
  animation: fallout 0.75s forwards;
  position: absolute;
  z-index: 999;
}

@keyframes fallout {
  0% {
    -webkit-transform: perspective(1000px) rotateX(90deg) rotateY(30deg)
      rotate(50deg) translateY(-100px) scale(0.8);
  }
  50% {
    -webkit-transform: perspective(1000px) rotateX(0deg) translateY(50px)
      scale(0.8);
  }
  100% {
    -webkit-transform: perspective(1000px) rotateX(0deg) translateY(-100px)
      translateX(500px) scale(1.1);
  }
}

@keyframes fallin {
  0% {
    -webkit-transform: perspective(1000px) rotateX(0deg) translateY(-100px)
      translateX(500px) scale(1.1);
  }
  50% {
    -webkit-transform: perspective(1000px) rotateX(0deg) translateY(50px)
      scale(0.8);
  }
  100% {
    -webkit-transform: perspective(1000px) rotateX(85deg) rotateY(10deg)
      translateY(-100px) scale(0.8);
  }
}

.contact h1 {
  margin-top: 0px;
}

a {
  margin: 10px;
}
</style>
