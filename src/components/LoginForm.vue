<template>
  <div id="login">
    <h1>{{ msg }}</h1>
    <form @submit.prevent="handleSubmit">
      <h1>{{ title }}</h1>
      <CustomInput v-bind:label="emailLable" :type="emailType" v-model="email" />
      <CustomInput v-bind:label="passwordLable" :type="passwordType" v-model="password" />
      <CustomInput v-for="(input, i) in inputs" :key="i"
                    v-model="input.value"
                    :label="input.label"
                    :type="input.type" />
      <button>Log in</button>
    </form>
  </div>
</template>
<style>
#login {
  text-align: left;
}
input {
  margin: 10px;
  display: block;
}
</style>
<script>
import CustomInput from '@/components/CustomInput.vue'
export default {
  name: 'LoginForm',
  data () {
    return {
      title: 'Login Form',
      inputs: [
        {
          label: 'postcode',
          value: '',
          type: 'text'
        },
        {
          label: 'address',
          value: '',
          type: 'text'
        },
        {
          label: 'Company key',
          value: '',
          type: 'password'
        }
      ],
      email: 'garywhitewolf@gmail.com',
      password: 'sd',
      emailLable: 'Email',
      passwordLable: 'Password',
      emailType: 'email',
      passwordType: 'password'
    }
  },
  methods: {
    handleSubmit () {
      console.log(this.email, this.password, this.inputs[0].value)
    }
  },
  props: {
    msg: String
  },
  components: {
    CustomInput
  }
}
</script>
