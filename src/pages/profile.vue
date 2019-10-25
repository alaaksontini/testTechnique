<template>
  <div class="q-pa-md">
    <q-card class="my-card" >
      <q-markup-table>
        <thead>
          <tr>
            <th class="text-left">User Profile</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td class="text-left text-weight-bold">Name</td>
            <td class="text-left"  >{{userInfo.name}}</td>
          </tr>
          <tr>
            <td class="text-left text-weight-bold">Username</td>
            <td class="text-left"  >{{userInfo.username}}</td>
          </tr>
          <tr>
            <td class="text-left text-weight-bold">Email</td>
            <td class="text-left">{{userInfo.email}}</td>
          </tr>
          <tr>
            <td class="text-left text-weight-bold">Address</td>
            <td class="text-left"  >{{userInfo.address.city}}</td>
          </tr>
          <tr>
            <td class="text-left text-weight-bold">Phone</td>
            <td class="text-left">{{userInfo.phone}}</td>
          </tr>
          <tr>
            <td class="text-left text-weight-bold">Website</td>
            <td class="text-left">{{userInfo.website}}</td>
          </tr>
          <tr>
            <td class="text-left text-weight-bold">Company</td>
            <td class="text-left">{{userInfo.company.name}}</td>
          </tr>
        </tbody>
      </q-markup-table>
    </q-card>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  name: 'PageIndex',
  data () {
    return {
      userInfo: {
        address: {
          city: ''
        },
        company: {
          name: ''
        }
      }
    }
  },
  mounted () {
    axios
      .get('https://jsonplaceholder.typicode.com/users/1')
      .then(response => {
        this.userInfo = response.data
      })
      .catch(error => {
        console.log(error)
        this.errored = true
      })
  },
  components: {
  }
}
</script>
<style lang="sass" scoped>
.my-card
  width: 500px
  max-width: 500px
</style>
