<template>
  <q-page class="bg-light-blue-13">
    <div class ="row">
      <q-card class ="fixed-center col-md-4 col-xs-12 bg-white">
        <q-card-section>
          <div class ="text-h6 q-pb-md">
          APP PENJUALAN BUKU
          </div>
          <q-form
            @submit="onSubmit"
            @reset="onReset"
            class="q-gutter-md"
          >
            <q-input
              filled
              v-model="username"
              label="Username Anda"
              lazy-rules
              :rules="[ val => val && val.length > 0 || 'Tolong Ketik Username']"
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
              <q-btn label="Submit" type="submit" color="primary"/>
              <q-btn label="Register" to="/register" color="warning" flat class="q-ml-sm"/>
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
      password: null
    }
  },
  methods: {
    onSubmit () {
      if (this.username === 'okecandra' && this.password === '12345') {
        this.$q.notify({
          type: 'positive',
          message: 'Berhasil Login'
        })
        this.$router.push('/home')
      } else {
        this.$q.notify({
          type: 'negative',
          message: 'Gagal Login'
        })
      }
    },
    onReset () {
      console.log('Ini fungsi Reset')
    }
  }
}
</script>
