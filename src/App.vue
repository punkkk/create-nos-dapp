<template>
    <div id="app">
        <div v-if="nos !== null">
            <app-header :title="title" :nos="nos"></app-header>
            <router-view :nos="nos"/>
        </div>
        <div v-else>
            Launch me through nOS client, please!
        </div>
    </div>
</template>

<script>
import AppHeader from './components/app-header'
const nosApi = window.NOS ? window.NOS.V1 : null

export default {
  name: 'app',
  components: { AppHeader },

  data: function () {
    return {
      nos: nosApi,
      title: 'nOS dapp'
    }
  }
}
</script>

<style lang="css">
</style>
