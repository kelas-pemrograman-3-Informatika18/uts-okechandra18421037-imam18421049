<template>
  <q-page padding>
  <q-table
      title="Penjualan Buku"
      :data="data"
      :columns="columns"
      row-key="name"
    >
      <template v-slot:body="props">
        <q-tr :props="props">
          <q-td key="props" :props="Judul">
            {{ props.row.Judul }}
          </q-td>
          <q-td key="Penerbit" :props="Penerbit">
            {{ props.row.Penerbit }}
          </q-td>
          <q-td key="fat" :props="Jumlah">
            {{ props.row.Jumlah }}
          </q-td>
          <q-td key="carbs" :props="Harga">
           <div class="row">
            <div class="col">
           <q-btn label="Edit" color="orange" icon="edit" uneleveted></q-btn>
           </div>
           <div class="col">
           <q-btn label="Hapus" color="negative" icon="delete" uneleveted></q-btn>
           </div>
           </div>
          </q-td>
        </q-tr>
      </template>
    </q-table>
  </q-page>
</template>

<script>
export default {
  name: 'Pageindex',
  data () {
    return {
      columns: [
        {
          name: 'Judul',
          required: true,
          label: 'Judul',
          align: 'left',
          field: 'Judul',
          sortable: true
        },
        { name: 'Judul', align: 'center', label: 'judul', field: 'judul', sortable: true },
        { name: 'Penerbit', label: 'Penerbit', align: 'center', field: 'Penerbit', sortable: true },
        { name: 'Jumlah', label: 'Jumlah', align: 'center', field: 'Jumlah', sortable: true },
        { name: 'Harga', label: 'Harga', align: 'center', field: 'Harga', sortable: true },
      ],
      data: [
        {
          Judul: 'Pendidikan Kewarganegaraan',
          Penerbit: 'Airlangga',
          Jumlah: '3',
          Harga: '25000000'
        }
      ]
    }
  }
}
</script>
