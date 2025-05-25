<template>
  <v-dialog v-model="show" max-width="400px" persistent>
    <v-card>
      <v-card-title class="headline">Login</v-card-title>
      <v-card-text>
        <v-form ref="form" v-model="valid">
          <v-text-field v-model="username" label="Username" :rules="[v => !!v || 'Username is required']" outlined dense
            required />
          <v-text-field v-model="password" label="Password" type="password"
            :rules="[v => !!v || 'Password is required']" outlined dense required />
          <v-alert v-if="error" type="error" dense class="mt-2">
            {{ error }}
          </v-alert>
        </v-form>
      </v-card-text>
      <v-card-actions>
        <v-spacer />
        <v-btn text @click="close">Cancel</v-btn>
        <v-btn :disabled="!valid" color="primary" @click="submit">Login</v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  props: {
    value: Boolean, // Controls show/hide
  },
  data() {
    return {
      show: this.value,
      username: '',
      password: '',
      valid: false,
      error: '',
      credentials: null,
    }
  },
  watch: {
    value(val) {
      this.show = val
    },
    show(val) {
      this.$emit('input', val)
      if (!val) this.reset()
    },
  },
  async mounted() {
    try {
      const res = await this.$axios.get('/login.json')
      this.credentials = res.data
    } catch {
      // fallback credentials
      this.credentials = { username: 'admin', password: '1234' }
    }
  },
  methods: {
    close() {
      this.show = false
    },
    submit() {
      if (
        this.credentials &&
        this.username === this.credentials.username &&
        this.password === this.credentials.password
      ) {
        this.error = ''
        this.$emit('login-success')
        this.close()
      } else {
        this.error = 'Invalid username or password'
      }
    },
    reset() {
      this.username = ''
      this.password = ''
      this.error = ''
      if (this.$refs.form) this.$refs.form.resetValidation()
    },
  },
}
</script>
