<template>
  <div>
    <form @submit.prevent>
      <input-text label="First name" id="first-name" v-model="person.first_name"/>
      <input-text label="Last name" id="last-name" v-model="person.last_name"/>
      <input-text label="Date of birth" id="date-of-birth" v-model="person.date_of_birth"/>

      <button @click="resetForm">Reset</button>
      <button type="submit" @click="submitForm">Submit</button>
    </form>

    <p v-if="isNotFull">
      {{person.last_name}} {{person.first_name}}, {{person.date_of_birth}}
    </p>
  </div>
</template>

<script>
import InputText from "@/components/InputText";

export default {
  name: 'App',
  components: {
    InputText
  },
  data() {
    return {
      person: {
        first_name: '',
        last_name: '',
        date_of_birth: ''
      }
    }
  },
  methods: {
    resetForm() {
      this.person.first_name = '';
      this.person.last_name = '';
      this.person.date_of_birth = '';
    },
    submitForm() {
      if(this.isNotFull) {
        console.info(`${this.person.last_name} ${this.person.first_name}, ${this.person.date_of_birth}`);
      } else {
        console.error(`this.person is null`);
      }
    }
  },
  computed: {
    isNotFull() {
      return this.person.first_name && this.person.last_name && this.person.date_of_birth;
    }
  }
}
</script>

<style>
form {
  font-family: Arial, sans-serif;
  font-size: 20pt;
  padding: 10px;
  margin: auto 30px;
}
p {
  font-family: Arial, sans-serif;
  font-size: 20pt;
  color: darkblue;
}
</style>
