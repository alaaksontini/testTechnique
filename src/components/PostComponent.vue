<template>
  <div class="q-pa-md">
    <q-table
      title="Posts"
      :data="data"
      :columns="columns"
      no-data-label="No Posts Found."
    >
  <template slot="top-selection">
    <q-btn color="secondary" flat label="Action 1" class="q-mr-sm" />
    <q-btn color="secondary" flat label="Action 2" />
    <div class="col" />
    <q-btn color="negative" flat round delete icon="delete" />
  </template>
    </q-table>
  </div>
</template>
<script>
export default {
  beforeUpdate () {
    this.tabval = this.value
    console.log('this.tabval  ', this.tabval)
  },
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
        { name: 'Actions', align: 'left', label: 'Actions', html: true }
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
