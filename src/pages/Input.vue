<template>
    <q-page padding>
    <q-card flat>
         <q-card-section class="q-gutter-md">
             <div class="text-h5">Input</div>
             <q-form
                  @submit="onSubmit"
                  @reset="onReset"
                  class="q-mt-lq"
                  >
                  <div class="q-gutter-md">
                  <q-input label="Judul Buku" v-model="Judul" filled :rules="[ val => val && val.length > 0 || 'Tolong Isi Judul Buku']"></q-input>
                  <q-input label="Penerbit Buku" v-model="Penerbit" filled :rules="[ val => val && val.length > 0 || 'Tolong Isi Penerbit Buku']"></q-input>
                  <q-input label="Jumlah Buku" v-model="Jumlah" filled :rules="[ val => val && val.length > 0 || 'Tolong Isi Jumlah Buku Dibeli']"></q-input>
                  <q-input label="Harga Buku" v-model="Harga" filled :rules="[ val => val && val.length > 0 || 'Tolong Isi Harga Buku']"></q-input>
                  <q-btn type="submit" label="Input" color="red" unelevated></q-btn>
                  <q-btn type="reset" label="Reset" color="red" flat unelevated></q-btn>
                  </div>
             </q-form>
         </q-card-section>
        </q-card>
    </q-page>
</template>
<script>
export default {
  data () {
    return {
      Judul: null,
      Penerbit: null,
      Jumlah: null,
      Harga: null
    }
  },
  methods: {
    onReset () {
      this.Judul = null
      this.Penerbit = null
      this.Jumlah = null
      this.Harga = null
    },
    onSubmit () {
      this.$q.notify({
        type: 'positive',
        message: 'Berhasil Input'
      })
      this.$router.push({ name: 'dashboard' })
    }
  }
}
</script>
