<template>
  <h1>Vue forms</h1>
  <form>
    <label for="email">Email</label>
    <input type="email" v-model="email" />

    <label for="password">Password</label>
    <input type="password" v-model="password" />

    <label for="role">Role</label>
    <select name="role" id="role" v-model="role">
      <option value="designer">Web Designer</option>
      <option value="developer">Web Developer</option>
    </select>

    <label for="skills">Skills</label>
    <input id="skills" type="text" v-model="tempSkill" @keyup.alt="addSkill" />
    <div v-for="skill in skills" :key="skill" class="pill">
      <span @click="removeSkill(skill)">{{ skill }}</span>
    </div>
    <br />

    <input type="checkbox" v-model="terms" required />
    <label for="terms">Accept terms & conditions</label>
  </form>

  <p>Email: {{ email }}</p>
  <p>Password: {{ password }}</p>
  <p>Role: {{ role }}</p>
  <p>Terms: {{ terms }}</p>
  <p>TempSkill: {{ tempSkill }}</p>
</template>

<script>
export default {
  name: 'App',
  components: {},
  data() {
    return {
      email: '',
      password: '',
      role: '',
      terms: false,
      tempSkill: '',
      skills: [],
    };
  },
  methods: {
    addSkill(e) {
      if (e.key === ',' && this.tempSkill) {
        if (!this.skills.includes(this.tempSkill)) {
          this.skills.push(this.tempSkill);
        }
        this.tempSkill = '';
      }
    },
    removeSkill(selectedSkill) {
      this.skills = this.skills.filter((skill) => skill !== selectedSkill);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body {
  margin: 0;
  background: #eee;
}
form {
  max-width: 420px;
  background: #fff;
  padding: 40px;
  margin: 30px auto;
  border-radius: 20px;
  text-align: left;
}
label {
  display: inline-block;
  color: #aaa;
  text-transform: uppercase;
  font-weight: 1.2rem;
}
input,
select {
  display: block;
  width: 100%;
  border: none;
  padding: 10px;
  border-bottom: 1px solid #ddd;
  margin: 15px 0 30px;
  box-sizing: border-box;
}
input[type='checkbox'] {
  position: relative;
  display: inline-block;
  width: 5%;
  margin-right: 20px;
}
.pill {
  display: inline-block;
  text-align: center;
  background: #ddd;
  letter-spacing: 1px;
  color: #333;
  padding: 5px 15px;
  border-radius: 20px;
  margin: 5px;
  cursor: pointer;
  font-weight: bold;
}
</style>
