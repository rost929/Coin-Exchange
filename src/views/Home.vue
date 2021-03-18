<template>
  <div>
    <px-assets-table v-bind:assets="assets" />
  </div>
</template>

<script>
import api from '@/api.js'
import PxAssetsTable from '@/components/PxAssetsTable'

export default {
  name: 'Home',
  components: { PxAssetsTable },
  data() {
    return {
      assets: []
    }
  },
  created() {
    console.log('Created...')
    api
      .getAssets()
      .then(assets => (this.assets = assets))
      .catch(error => console.log(error))
  }
}
</script>
