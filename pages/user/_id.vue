<template>
  <div>
    {{user.id}} {{user.created | timeSince }}
  </div>
</template>

<script>
  import axios from '~/plugins/axios'

  export default {
    async asyncData({route}) {
      console.log('ROUTE PARAMS', route.params)
      const res = await axios.get(`user/${route.params.id}`.json)
      return { user: res.data }
    }
  }
</script>
