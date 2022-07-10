<template>
  <div>
    <div id="header" class="bg-[url('/DeepSkyBlue.jpg')] px-20">
      <div id="menu" class="grid grid-cols-2">
        <div id="menu-left">
          <NuxtLink to="/"><img src="/QorvoLogo4.png" class="w-[200px]" alt="" /></NuxtLink>
        </div>
        <div id="menu-right">
          <ul class="md:grid grid-cols-4 text-lg font-oswald uppercase pt-10">
            <li class="text-white">Hardware</li>
            <li class="text-white">Instrument</li>
            <NuxtLink to="/menu" class="text-white">Components</NuxtLink>
            <NuxtLink to="/cart" class="text-white">Cart ({{ $store.getters.totalItems }})</NuxtLink>
          </ul>
        </div>
      </div>
      <div>
        <div class="py-20">
          <h1
            class="text-6xl text-white text-center font-oswald uppercase pt-24 pb-28"
          >
            Coupler
          </h1>
        </div>
      </div>
    </div>
    <div id="items" class="md:grid grid-cols-10 gap-x-5 gap-y-16 mt-10 mx-50 lg:grid grid-cols-10 gap-x-5 gap-y-16 mt-10 mx-50 xl:grid grid-cols-10 gap-x-5 gap-y-16 mt-10 mx-50">
      <MenuItem1 v-for="b in items" :key="b.name" :item="b" />
    </div>
  </div>
</template>

<script>
import MenuItem1 from '~/components/MenuItem1.vue';
export default {
  data() {
    return {
      items: [],
    };
  },
  mounted() {
    this.$axios.get('items.json').then((response) => {
      this.items = response.data.coupler;
    });
  },
  components: { MenuItem1 },
};
</script>
