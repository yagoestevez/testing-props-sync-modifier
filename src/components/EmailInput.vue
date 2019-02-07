<template>
  <input type="text" @input="handleLazyInput" placeholder="Type your email">
</template>

<script>
  export default {
    name: 'EmailInput',
    data ( ) {
      return { timeout: null }
    },
    methods: {
      handleLazyInput ( event ) {
        clearTimeout( this.timeout );
        this.timeout = setTimeout( ( ) => {
          this.$emit( 'update:email', event.target.value )
        }, 500 );
      }
    }
  }
</script>