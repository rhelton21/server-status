<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12">
                <head-title></head-title>
            </div>
        </div>
        <hr>
        <div class="row">
            <div class="col-xs-12 col-sm-6">
                <ul class="list-group">
                    <server></server>
                </ul>
            </div>
           <server-detail></server-detail>
        </div>
        <hr>
        <div class="row">
            <server-manage></server-manage>
        </div>
    </div>
</template>

<script>
import headTitle from './shared/head.vue'
import server from './server/server.vue'
import serverDetail from './server/serverDetail.vue'
import serverManage from './shared/serverManage.vue'

export default {
  name: 'app',
  data () {
    return {
      msg: ''
    }
  },
  components: {
    headTitle,
    server,
    serverDetail,
    serverManage
  }
}
</script>

<style>

</style>
