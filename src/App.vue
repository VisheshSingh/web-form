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

    <input type="checkbox" v-model="terms" />
    <label for="terms">Accept terms & conditions</label>

    <div>
      <input type="checkbox" value="shaun" v-model="names" />
      <label for="names">shaun</label>
      <input type="checkbox" value="yoshi" v-model="names" />
      <label for="names">yoshi</label>
      <input type="checkbox" value="mario" v-model="names" />
      <label for="names">mario</label>
    </div>
  </form>

  <p>Email: {{ email }}</p>
  <p>Password: {{ password }}</p>
  <p>Role: {{ role }}</p>
  <p>Terms: {{ terms }}</p>
  <p>Names: {{ names }}</p>
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
      names: [],
    };
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
</style>
