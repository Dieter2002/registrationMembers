<template>
  <div>
    <div class="centerTest">
      <div>{{ month }}</div>

      <div class="days" v-for="item in constdaysOfWeek" :key="item.day">
        <h3>{{ item.day }}</h3>
      </div>

      <div class="marginDays">
        <div class="marginBlocks" v-for="index in 5" :key="index">
          <div
            class="test"
            v-for="index in numberOfDays"
            :key="index"
            v-on:click="openModel"
          >
            &nbsp; {{ 1 }}
          </div>
        </div>
      </div>

      <!-- ------------------------------------- -->

      <!-- The Modal -->
      <div ref="myModel" class="modal">
        <!-- Modal content -->
        <div class="modal-content">
          <div class="modal-header">
            <span v-on:click="closeModel" class="close">&times;</span>
            <h2>Modal Header</h2>
          </div>
          <div class="modal-body">
            <div v-for="item in dashboard" :key="item.id">
              <h3>{{ item.id }}</h3>
            </div>
          </div>
          <div class="modal-footer">
            <h3>Modal Footer</h3>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// var modal = this.$refs.myModel
// modal.style.display = "block";
// var span = document.getElementsByClassName("close")[0];

// span.onclick = function () {
//   this.$refs.myModel.style.display = "none";
// };

export default {
  name: "dashboard",
  props: ["dashboard"],

  data() {
    return {
      constdaysOfWeek: [
        { day: "Sunday" },
        { day: "Monday" },
        { day: "Tuesday" },
        { day: "Wednesday" },
        { day: "Thursday" },
        { day: "Friday" },
        { day: "Saturday" },
      ],
      numberOfDays: 7,
      month:
        new Date()
          .toLocaleString("default", { month: "long" })
          .charAt(0)
          .toUpperCase() +
        new Date()
          .toLocaleString("default", { month: "long" })
          .slice(1),
    };
  },
  methods: {
    openModel: function () {
      this.$refs.myModel.style.display = "block";
    },
    closeModel: function () {
      this.$refs.myModel.style.display = "none";
    },
  },
};
</script>

    


<style>
@import url("https://fonts.googleapis.com/css?family=Roboto:700");
@import url(https://fonts.googleapis.com/css?family=Khula:700);

.centerTest {
  margin: auto;
  margin-top: 120px;
  height: 35pc;
  width: 60%;
  border-radius: 25px;
  background-color: #f7f5f5;
  font-family: Khula;
}

.days {
  float: left;
  border: 3px white;
  padding-left: 48px;
  padding-top: 50px;
  /* font-family: "Lato", sans-serif; */
}

.marginDays {
  padding-top: 50px;
  padding-left: 40px;
  /* color: black; */
  /* overflow: hidden; */
  /* background-color: blue; */
}

.marginBlocks {
  margin-bottom: 45px;
}

.test {
  float: left;
  background-color: white;
  width: 110px;
  height: 80px;
  /* padding: auto; */
  margin-left: 5px;
  margin-top: 5px;
  /* padding-top: 100px; */
}

.test:hover {
  transform: scale(0.9);
  background-color: yellow;
}

/* ------------------ Model --------------------*/

/* The Modal (background) */
.modal {
  display: none;
  position: fixed;
  z-index: 1;
  padding-top: 100px;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgb(0, 0, 0);
  background-color: rgba(0, 0, 0, 0.4);
}

/* Modal Content */
.modal-content {
  position: relative;
  background-color: #fefefe;
  margin: auto;
  padding: 0;
  border: 1px solid #888;
  width: 80%;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  -webkit-animation-name: animatetop;
  -webkit-animation-duration: 0.4s;
  animation-name: animatetop;
  animation-duration: 0.4s;
}

/* Add Animation */
@-webkit-keyframes animatetop {
  from {
    top: -300px;
    opacity: 0;
  }
  to {
    top: 0;
    opacity: 1;
  }
}

@keyframes animatetop {
  from {
    top: -300px;
    opacity: 0;
  }
  to {
    top: 0;
    opacity: 1;
  }
}

/* The Close Button */
.close {
  color: white;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
}

.modal-header {
  padding: 2px 16px;
  background-color: #5cb85c;
  color: white;
}

.modal-body {
  padding: 2px 16px;
}

.modal-footer {
  padding: 2px 16px;
  background-color: #5cb85c;
  color: white;
}
</style>