<template>
  <div>
    <form>
      <input-text label="First name" id="first-name" v-model="person.first_name"/>
      <input-text label="Last name" id="last-name" v-model="person.last_name"/>
      <input-text label="Date of birth" id="date-of-birth" v-model="person.date_of_birth"/>
    </form>

    <p v-if="person.last_name && person.first_name && person.date_of_birth">
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
