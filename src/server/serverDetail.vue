<template>
  <div>
    <div class="col-xs-12 col-sm-6">
      <p v-if='server==null'>Server Details are currently not updated</p>
      <p v-else> The server status of the server {{server.id}} is {{server.status}}</p>
    </div>
    <br>
    <div v-if="server!==null">
      <div class="form-group">
        <label for="sel1">Select status:</label>
        <select class="form-control" id="sel1" v-model='selected'>
          <option v-for='status in statusOptions'> {{status}} </option>
        </select>
      </div>
      <button @click="changeServerStatus">Change server status</button>
    </div>
  </div>	
</template>

<script>
import {eventBus} from '../main'

export default {
  data () {
    return {
      server: null,
      selected:'',
      statusOptions: [
        'online',
        'offline',
        'unknow'
      ]
    }
  },
  methods:{
    changeServerStatus () {
      this.server.status = this.selected
    }
  },
  created () {
    eventBus.$on('changeServer', (server) => {
      this.server = server
      this.selected = server.status
    })
  } 
}
</script>