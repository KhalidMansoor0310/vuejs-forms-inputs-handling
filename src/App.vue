<template>
  <div :class="formdiv">
    <h3>Vue Js Form-Handling</h3>
    <form>
      <div>
        <input type="text" placeholder="username" v-model="name" />
      </div>
      <div>
        <input type="text" placeholder="email" v-model="email" />
      </div>

      <div>
        <input type="text" placeholder="password" v-model="password" />
      </div>

      <div>
        <select v-model="role">
          <option value="web developer">Web Developer</option>
          <option value="web designer">Web Designer</option>
        </select>
      </div>
      <div :class="terms">
        <input type="checkbox" v-model="terms" />
        <label for="">Accept the Terms and Conditions</label>
      </div>

      <div>
        <input type="checkbox" value="vue js" v-model="names" />
        <label for="">Vue Js</label>
      </div>

      <div>
        <input type="checkbox" value="react js" v-model="names" />
        <label for="">React JS</label>
      </div>

      <div>
        <input type="checkbox" value="angular js" v-model="names" />
        <label for="">Angular Js</label>
      </div>

      <div>
        <input
          type="text"
          placeholder="enter space for new skill"
          v-model="tempSkill"
          @keyup="addSkill"
        />
        <ul v-for="skill in skills" :key="skill">
          <li>{{ skill }}</li>
        </ul>
      </div>

      <br />
      name:{{ name }} <br />
      email:{{ email }} <br />
      password:{{ password }} <br />
      role:{{ role }}br terms:{{ terms }} <br />
      names:{{ names }} <br />
    </form>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: "",
      email: "",
      password: "",
      role: "",
      terms: false,
      names: [],
      tempSkill: "",
      skills: [],
    };
  },
  methods: {
    addSkill(e) {
      if (e.key === " " && this.tempSkill) {
        if (!this.skills.includes(this.tempSkill)) {
          this.skills.push(this.tempSkill);
        }
        this.tempSkill = "";
      }
    },
  },
};
</script>

<style>
#app {
  text-align: center;
  padding: 0%;
  margin: 0%;
  background-color: #eee;
  height: 100vh;
  box-sizing: border-box;
}
.formdiv {
  background-color: #eee;
}
form {
  width: 30%;
  margin: 60px auto;
  text-align: left;
}

ul {
  display: flex;
}
li {
  display: flex;
  list-style: none;
}

input[type="text"] {
  padding: 12px;

  border: 1px solid black;
}
input[type="checkbox"] {
  display: inline-block;
  width: 12px;
  padding: 10px;
}
select {
  padding: 12px;
}
div {
  display: flex;
  flex-direction: column;
  margin-bottom: 20px;
}
</style>
