<template>
  <div>
    <li
    style="cursor: pointer"
    class="list-group-item"
    @click="serverDetail(server)"
    v-for="server in servers">
    Server #{{ server.id }}
  </li>
</div>
</template>
<script>
import {eventBus} from '../main'

export default {
  data () {
    return {
      servers:[
        {
          id:1 , status:'online'
        },
        {
          id:2 , status:'offline'
        },
        {
          id:3 , status:'unknow'
        }
      ]
    }
  },
  methods: {
    serverDetail (server) {
      eventBus.$emit('changeServer',server)
    }
  }
}
</script>
<style>

</style>