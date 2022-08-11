<template>
  <div class="mx-auto container-fluid">
    <h3 class="mt-5">Hello, {{ name }}!</h3>

    <div v-if="$store.state.isStoreSelected == false && $store.state.storeInfo.length != 0">
      <p>Please select your store</p>
      <button class="btn btn-dark" @click="$emit('openModal')">Select</button>
    </div>
        <div v-if="$store.state.storeInfo.length == 0">
      <p>You are not registered in any store.<br/>
Please create a store or ask your manager to add you to the store.</p>
      <button class="btn btn-dark" @click="$emit('openModal')">Create</button>
    </div>
  </div>
</template>

<script>
import {computed} from "vue"
import router from "../router.js";
export default {
  name: "home-view",
  data() {
    return {
      name: computed(()=>this.$store.state.user.firstName),
      storeFecthed: computed(()=>this.$store.state.storeInfo.length)
    };
  },
  components: {},
  methods: {},
};
</script>

<style></style>
