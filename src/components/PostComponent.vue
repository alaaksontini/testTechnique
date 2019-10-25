<template>
  <div class="q-pa-md">
    <q-table
      title="Posts"
      :data="data"
      :columns="columns"
      no-data-label="No Posts Found."
    >
    </q-table>
  </div>
</template>
<script>
export default {
  props: ['value'],
  data () {
    return {
      columns: [
        {
          name: 'name',
          required: true,
          label: 'Title',
          align: 'left',
          field: 'title',
          format: val => `${val}`,
          sortable: true
        },
        { name: 'Description', align: 'left', label: 'Description', field: 'body', sortable: true, style: 'white-space: normal' },
        { name: 'Actions', align: 'left', label: 'Actions'}
      ],
      rows: [
        {
          btn: '<button>My Action</button>'
        }
      ],
      data: this.value
    }
  }
}
</script>
