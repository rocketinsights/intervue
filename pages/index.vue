<template>
  <section class="container">
    <div>
      <app-logo />
      <h1 class="title">Intervue</h1>
    </div>
  </section>
</template>

<script>
import axios from 'axios'
import AppLogo from '@/components/AppLogo.vue'

export default {
  components: {
    AppLogo
  },
  async data () {
    const params = { text: 'optics' }
    const { data } = await axios.get('http://dev-meat-eater.pantheonsite.io/wp-json/wp/v2/posts', { params })
    console.log(data)
    // before page renders state stuff
    return { data }
  },
  computed: {},
  methods: {},
  mounted () {}
}
</script>

<style scoped>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}
</style>

