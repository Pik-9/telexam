<template>
  <v-container>
    <v-row>
      <v-col>
        <v-text-field v-model="username" label="Username"></v-text-field>
      </v-col>
    </v-row>

    <v-row>
      <v-col>
        <v-text-field
          v-model="password"
          type="password"
          label="Password"
        ></v-text-field>
      </v-col>
    </v-row>

    <v-row>
      <v-col>
        <v-btn @click="sendLogin()">Login</v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    async sendLogin() {
      const response = await this.$axios.post('/login', {
        username: this.username,
        password: this.password
      })
      console.log(`Got response:`)
      console.dir(response)
    }
  }
}
</script>
