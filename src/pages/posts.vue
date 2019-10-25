 <template>
 <q-card
      class="my-card text-white"
      style="background: radial-gradient(circle, #35a2ff 0%, #014a88 100%); height: fit-content;;
">
    <posts v-if="userInfo.length" v-bind:value="userInfo"></posts>
    </q-card>
 </template>
<script>
import PostComponent from 'src/components/PostComponent.vue'
import axios from 'axios'
// import CommentsComponent from 'src/components/CommentsComponent.vue'
export default {
  name: 'PageIndex',
  data () {
    return {
      userInfo: []
    }
  },
  mounted () {
    axios
      .get('https://jsonplaceholder.typicode.com/posts')
      .then(response => {
        this.userInfo = response.data
      })
      .catch(error => {
        console.log(error)
        this.errored = true
      })
  },
  components: {
    'posts': PostComponent
    // 'comments': CommentsComponent
  }
}
</script>
