<template>
  <div class="home">
    <api />
  </div>
</template>

<script>
import api from '../components/blog';
export default {
  name: 'Home',
  components: {
    api
  }
}
</script>
