<template>
  <div class="dashboard">
    <Test mrg="Dashboard" />
    <ToggleSidebar />
    
  </div>
</template>

<script>
import Test from "@/components/test.vue";
import ToggleSidebar from '@/components/toggle_sidebar.vue';

export default {
  components: {
    Test,
    ToggleSidebar
  },
  setup() {
    return {}
  },
};
</script>
