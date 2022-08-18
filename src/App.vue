<template>
  <div>
    <form>
      <div>
        <label for="first-name">First name</label>
        <input type="text" id="first-name" v-model="person.first_name">
      </div>
      <div>
        <label for="last-name">Last name</label>
        <input type="text" id="last-name" v-model="person.last_name">
      </div>
      <div>
        <label for="date-of-birth">Date of birth</label>
        <input type="text" id="date-of-birth" v-model="person.date_of_birth">
      </div>
    </form>

    <p v-if="person.last_name && person.first_name && person.date_of_birth">
      {{person.last_name}} {{person.first_name}}, {{person.date_of_birth}}
    </p>
  </div>
</template>

<script>
export default {
  name: 'App',
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
input{
  font-family: Arial, sans-serif;
  font-size: 20pt;
}
div {
  margin: 10px;
  padding: 5px;
}

label {
  margin: 3px;
}

p {
  font-family: Arial, sans-serif;
  font-size: 20pt;
  color: darkblue;
}
</style>
