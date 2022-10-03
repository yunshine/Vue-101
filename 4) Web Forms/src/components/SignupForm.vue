<template>
  <form>
    <label>Email:</label>
    <input type="email" required v-model="email_address">

    <label>Password:</label>
    <input type="password" required v-model="password">

    <label>Role:</label>
    <select v-model="role">
      <option value="Web Developer">Web Developer</option>
      <option value="Web Designer">Web Designer</option>
      <option value="Project Manager">Project Manager</option>
    </select>

    <label>Skills: (press "," after each skill)</label>
    <input type="text" v-model="tempSkill" @keyup="addSkill">
  
    <div class="terms_and_conditions">
      <input type="checkbox" required v-model="terms">
      <label>Accept Terms And Conditions</label>
    </div>

    <div class="names_list_array">
      <input type="checkbox" value="Yun" v-model="names">
      <label>Yun</label>
    </div>
    <div>
      <input type="checkbox" value="Eunjoo" v-model="names">
      <label>Eunjoo</label>
    </div>
    <div>
      <input type="checkbox" value="Noriko" v-model="names">
      <label>Noriko</label>
    </div>

    <div class="submit">
      <button>Create an Account</button>
    </div>
  </form>

  <p>{{ tempSkill }}</p>
  <p>{{ skills }}</p>
  <p>{{ terms }}</p>

  <div class="skills" v-for="skill in skills" :key="skill">
    <span @click="deleteSkill(skill)">{{ skill }}</span>
  </div>

</template>

<script>
export default {
  data() {
    return {
      email_address: '',
      password: '',
      role: 'Web Developer',
      terms: false,
      names: [],
      tempSkill: '',
      skills: []
    }
  },
  methods: {
    addSkill(e) {
      if (e.key === ',' && this.tempSkill) {
        if (!this.skills.includes(this.tempSkill.slice(0, -1))) {
          this.skills.push(this.tempSkill.slice(0, -1))
        }
      this.tempSkill = ''
      }
    },
    deleteSkill(item) {
      this.skills = this.skills.filter((skill) => {
        return skill !== item
      })
    }
  }
}
</script>

<style>
  form {
    max-width: 420px;
    margin: 30px auto;
    background: white;
    text-align: left;
    padding: 40px;
    border-radius: 8px;
  }
  label {
    color: #aaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
  }
  input, select {
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;
  }
  input[type="checkbox"] {
    display: inline-block;
    width: 16px;
    margin: 0 10px 0 0;
    position: relative;
    top: 1px
  }
  .skills {
    display: inline-block;
    margin: 20px 10px 0 0;
    padding: 6px 12px;
    background: #eee;
    border-radius: 20px;
    font-size: 12px;
    letter-spacing: 1px;
    font-weight: bold;
    color: #777;
    cursor: pointer;
  }
  button {
    background: #0b6dff;
    border: 0;
    padding: 10px 20px;
    margin-top: 20px;
    color: white;
    border-radius: 20px;
  }
  .submit {
    text-align: center;
  }
</style>