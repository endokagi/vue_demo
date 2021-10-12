<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <Test msg="Test Components"/>
  </div>

</template>

<script>
// @ is an alias to /src
import Test from '@/components/HelloWorld.vue'
export default {
  name: 'Home',
  components: {
    Test
  }
}
</script>
