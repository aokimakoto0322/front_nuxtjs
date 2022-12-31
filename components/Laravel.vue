<template>
  <div class="main" :style="mainStyle">
    <h1>Welcome!</h1>
    <div class="tabgroup">
      <ul class="tabnav">
        <li @click="show = '1'" v-bind:class="{'active': show == '1'}">
          login
        </li>
        <li @click="show = '2'" v-bind:class="{'active': show == '2'}">
          Register
        </li>
      </ul>
    </div>

    <div class="tabcontent">
      <div v-if="show == '1'" class="tabcontent-list">
        <input type="text" name="username" id="username" placeholder="User Name" :style="input"/>
        <br />
        <input type="password" name="password" id="password" placeholder="P@$$W0RD" :style="input"/>
        <br />
        <input type="button" value="login" class="button" id="login" :style="inputStyle"/>
        <br />
      </div>
      <div v-else-if="show == '2'" class="tabcontent-list">
        <input type="text" name="username" id="username" placeholder="User Name" :style="input"/>
        <br />
        <input type="password" name="password" id="password" placeholder="P@$$W0RD" :style="input"/>
        <br />
        <input type="button" value="Register" class="button" id="register" :style="inputStyle"/>
        <br />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Login",
  //Custom style for main and input for make the page responsive:
  props: {
    mainStyle: String,
    inputStyle: String,
  },
  data() {
    return {
      show: "1",
    }
  },
};
</script>

<style>
/* Import Poppins font: */
@import url("https://fonts.googleapis.com/css2?family=Poppins&display=swap");
.main {
  background: rgba(255, 255, 255, 0.4);
  position: absolute;
  top: 20%;
  left: 30%;
  width: 40%;
  text-align: center;
  padding: 5px;
  border-radius: 3rem;
  box-shadow: 0px 0px 8px -5px #000000;
  padding-top: 3%;
  padding-bottom: 5%;
  font-family: "Poppins", sans-serif;
}
.tabnav {
  margin: 0;
  padding: 0;
  display: flex;
  list-style-type: none;
}
.tabnav li {
  cursor: pointer;
  width: 50%;
  padding: 10px;
  text-decoration: none;
}
.tabnav li.active {
  background: #405dca;
  color: #fff;
}
.tabcontent {
  padding: 20px;
  border: 1px dotted #ccc;
}
h1 {
  cursor: default;
  user-select: none;
}
input {
  border-radius: 3rem;
  border: none;
  padding: 10px;
  text-align: center;
  outline: none;
  margin: 10px;
  width: 50%;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
  font-weight: 400;
}
input:hover {
  box-shadow: 0px 0px 8px -5px #000000;
}
input:active {
  box-shadow: 0px 0px 8px -5px #000000;
}
.button {
  cursor: pointer;
  user-select: none;
  background: lightgreen;
}
img {
  height: 2.2rem;
  margin: 10px;
  user-select: none;
}
img:hover {
  box-shadow: 0px 0px 8px -5px #000000;
  cursor: pointer;
  border-radius: 200rem;
}
</style>