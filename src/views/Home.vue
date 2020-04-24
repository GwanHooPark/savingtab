<template>
  <div class="home">
    <TabGroup/>
  </div>
</template>

<script>
// @ is an alias to /src
import TabGroup from "@/components/TabGroup.vue";

export default {
  name: "Home",
  components: {
    TabGroup
  }
};
</script>
