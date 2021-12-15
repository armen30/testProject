<template>
  <div>
    <b-container >
      <b-row>

        <b-col  cols="12">
          <input type="text" v-model="form.name">
          <input type="text" v-model="form.email">
          <input type="password" v-model="form.password">
          <b-button  @click="sendToBack" class=" btn-success">Registration</b-button>
        </b-col>
      </b-row>
    </b-container>

  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      form: {
        name:'',
        email: '',
        password: ''
      }
    }
  },
  methods: {
    sendToBack() {

      return new Promise((resolve, reject) => {
        axios.post('/auth/register', this.form)
          .then((result) => {
            console.log(result)
          })
          .catch(error => {
            console.log(error)
          })
      })


    }
  }
}


</script>

<style scoped>

</style>
