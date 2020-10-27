<template>
  <div class="hello">
    <!-- <b-button id="show-btn" @click="showModal">Open Modal</b-button> -->

    <!-- <b-modal hide-footer title="Using Component Methods">
      <div class="d-block text-center">
        <h3>Hello From My Modal!</h3>
      </div>
      <b-button class="mt-3" variant="outline-danger" block @click="hideModal"
        >Close Me</b-button
      >
    </b-modal> -->
    <b-input-group prepend="Nhập tên của bạn" class="mt-3">
      <b-form-input v-model="name"></b-form-input>
      <b-button @click="random" variant="info"
        >Đoán điểm kiểm tra của bạn =))</b-button
      >
    </b-input-group>

    <b-modal ref="my-modal">
      <div class="text-right cross"><i class="fa fa-times"></i></div>
      <div class="card-body text-center">
        <img src="https://img.icons8.com/bubbles/200/000000/trophy.png" />
        <h4 style="font-weight: bold">CONGRATULATIONS! {{ name }}</h4>
        <p>Ngày mai bạn sẽ đạt được {{ point }} điểm =))))</p>
      </div>
    </b-modal>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      name: "",
      arrPoint: [7, 7.5, 8, 8.5, 9, 9.5, 10],
      point: 7,
    };
  },
  props: {
    msg: String,
  },
  methods: {
    showModal() {
      this.$refs["my-modal"].show();
    },
    hideModal() {
      this.$refs["my-modal"].hide();
    },
    random() {
      this.$refs["my-modal"].show();
      const random = Math.floor(Math.random() * this.arrPoint.length);
      this.point = this.arrPoint[random];
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
body {
  background-color: #d32f2f;
  font-family: "Calibri", sans-serif !important;
}

.mt-100 {
  margin-top: 100px;
}

.container {
  margin-top: 200px;
}

.card {
  position: relative;
  display: flex;
  width: 450px;
  flex-direction: column;
  min-width: 0;
  word-wrap: break-word;
  background-color: #fff;
  background-clip: border-box;
  border: 1px solid #d2d2dc;
  border-radius: 4px;
  -webkit-box-shadow: 0px 0px 5px 0px rgb(249, 249, 250);
  -moz-box-shadow: 0px 0px 5px 0px rgba(212, 182, 212, 1);
  box-shadow: 0px 0px 5px 0px rgb(161, 163, 164);
}

.card .card-body {
  padding: 1rem 1rem;
}

.card-body {
  flex: 1 1 auto;
  padding: 1.25rem;
}

p {
  font-size: 14px;
}

h4 {
  margin-top: 18px;
}

.cross {
  padding: 10px;
  color: #d6312d;
  cursor: pointer;
}

.continue:focus {
  outline: none;
}

.continue {
  border-radius: 5px;
  text-transform: capitalize;
  font-size: 13px;
  padding: 8px 19px;
  cursor: pointer;
  color: #fff;
  background-color: #d50000;
}

.continue:hover {
  background-color: #d32f2f !important;
}
</style>
