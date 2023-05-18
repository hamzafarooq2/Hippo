<template>
  <div class="section">
    <div class="column">
      <h2>Instructions</h2>
      <p>
        => Don't open any new tab. <br />
        => Read the task carefully
      </p>
    </div>
    <div class="column">
      <h2>Task</h2>
      <p>Write a JavaScript function to print the “Hello World” message</p>
    </div>
    <div class="column">
      <h2>Answer</h2>
      <form @submit.prevent="submitCode()">
        <textarea
          v-model="codeInput"
          placeholder="Enter JavaScript code..."
        ></textarea>
        <button @click="[saveVideo]" value="submit" type="submit">
          Submit
        </button>
      </form>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Columns",
  data() {
    return {
      codeInput: "",
      isNewTabOpened: "false",
    };
  },
  created() {
    document.addEventListener("visibilitychange", (event) => {
      if (document.visibilityState == "visible") {
      } else {
        this.isNewTabOpened = true;
      }
    });
  },
  methods: {
    async submitCode() {
      try {
        await axios.post("http://localhost:3000/testReport", {
          text: this.codeInput,
          changeTab: this.isNewTabOpened,
        });
      } catch (error) {
        console.error(error);
      }
    },
  },
};
</script>

<style scoped>
.section {
  width: 100%;
  margin: 120px 0 0 60px;
  display: flex;
  justify-content: space-evenly;
  overflow: hidden;
}

.column {
  background-color: #f1f1f1;
  box-shadow: rgba(0, 0, 0, 0.16) 0px 10px 36px 0px,
    rgba(0, 0, 0, 0.06) 0px 0px 0px 1px;

  text-align: center;
  padding: 12px 22px 0 12px;
  height: 500px;
  width: 400px;
  border-radius: 12px;
  margin: 12px;
}
.column p {
  margin-top: 20px;
  color: slategray;
  font-weight: bold;
  font-size: 20px;
}
.column h2 {
  color: orangered;
}

textarea {
  width: 100%;
  margin-top: 16px;
  padding: 8px 0 0 8px;
  height: 390px;
  resize: none;
  border-radius: 4px;
  border-color: lightslategrey;
  border: 1 px solid slategray;
  outline: none;
  background-color: black;
  color: white;
}

button {
  display: flex;
  margin-top: 10px;
  padding: 8px 16px;
  background-color: teal;
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 4px;
}

@media only screen and (max-width: 890px) {
  .section {
    display: flex;
    flex-wrap: wrap;
    margin: 100px 0 0 50px;
  }
  .column {
    width: 300px;
  }
}
@media only screen and (max-width: 710px) {
  .section {
    display: flex;
    flex-wrap: wrap;
    margin: 80px 0 0 44px;
  }
}
@media only screen and (max-width: 500px) {
  .column {
    width: 300px;
    height: 450px;
  }
  textarea {
    height: 335px;
  }
}
@media only screen and (max-width: 406px) {
  .column {
    width: 260px;
    height: 390px;
  }
}
</style>
