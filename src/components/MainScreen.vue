<!--
  Learn more:
  https://medium.com/front-end-weekly/vues-v-model-directive-vs-sync-modifier-d1f83957c57c
-->
<template>
  <div>
    <h1>Testing props.sync modifier</h1>
    <div class="wrapper">
      <email-input :email.sync="email" />
      <alert :show="verifyEmail">Valid email. Yay!</alert>
    </div>
  </div>
</template>

<script>
  import EmailInput from '@/components/EmailInput.vue';
  import Alert      from '@/components/Alert.vue';

  export default {
    name: 'MainScreen',
    data () {
      return { timeout:null, email:'', valid:false }
    },
    components: {
      EmailInput,
      Alert
    },
    computed: {
      verifyEmail ( ) {
        const RE = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
        return RE.test( String( this.email ).toLowerCase( ) );
      }
    }
  }
</script>

<style scoped lang="scss">
  .wrapper {
    background: #eee;
    border: 1px solid #aaa;
    margin: auto;
    width: 300px;
    padding: 1rem;

    input {
      box-sizing: border-box;
      padding: 1rem;
      width: 100%;
      text-align: center;
      font-size: 2rem;
      border: 1px solid #aaa;
      outline: none;
    }
  }
</style>
