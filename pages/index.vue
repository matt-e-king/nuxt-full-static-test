<template>
  <div>
    <h1>Testing static generation</h1>
    <h2>Will this work?</h2>

    <ul>
      <li v-for="(l,i) in list" :key="i">{{ l }}</li>
    </ul>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  async asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          list: [1,2,3,4,5]
        })
      }, 10000)
    })
  },
  components: {
    Logo,
    VuetifyLogo
  },

  data () {
    return {
      list: []
    }
  }
}
</script>
