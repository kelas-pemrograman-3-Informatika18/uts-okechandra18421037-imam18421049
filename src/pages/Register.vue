<template>
  <q-page class="bg-light-blue-13">
    <div class ="row">
      <q-card class ="fixed-center col-md-4 col-xs-12 bg-white">
        <q-card-section>
          <div class ="text-h6 q-pb-md">
          Register Penjualan Buku
          </div>
          <q-form
            @submit="onSubmit"
            @reset="onReset"
            class="q-gutter-md"
          
            <q-input
              filled
              v-model="username"
              label="Username Anda"
              lazy-rules
              :rules="[ val => val && val.length > 0 || 'Tolong Ketik Username']"
            />

            <q-input
              filled
              v-model="namalengkap"
              label="Nama Lengkap Anda"
              lazy-rules
              :rules="[ val => val && val.length > 0 || 'Tolong Ketik Nama Lengkap']"
            />

            <q-input
              filled
              v-model="email"
              label="Email Anda"
              lazy-rules
              :rules="[ val => val && val.length > 0 || 'Tolong Ketik Email']"
            />

            <q-input
              filled
              type="password"
              v-model="password"
              label="Password Anda"
              lazy-rules
              :rules="[
                val => val !== null && val.length > 0 || 'Password Tidak Boleh Kosong'
              ]"
            />
            <div class="q-gutter-md">
              <q-btn label="Register" type="submit" color="primary"/>
              <q-btn label="Submit" to="/" color="warning" flat class="q-ml-sm"/>
              <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
            </div>
          </q-form>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>
<script>
export default {
  data () {
    return {
      username: null,
      password: null,
      namalengkap: null,
      email: null
    }
  },
  methods: {
    onSubmit () {
    },
    onReset () {
      this.username = null
      this.password = null
    }
  }
}
</script>
