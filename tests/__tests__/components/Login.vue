<template>
  <div>
    <form @submit.prevent="submit">
      <label for="username-input">Username</label>
      <input
        id="username-input"
        data-testid="username-input"
        v-model="username"
        placeholder="Username..."
        name="username" >
      <label id="password-label">Password</label>
      <input
        v-model="password"
        placeholder="Password..."
        type="password"
        name="password"
        aria-labelledby="password-label"
      >
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  props: {
    onSubmit: {
      type: Function,
      required: true
    }
  },
  data () {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    submit () {
      this.onSubmit({
        username: this.username,
        password: this.password
      })
    }
  }
}
</script>
