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
            Cart
          </h1>
        </div>
      </div>
    </div>

    <table class="table-auto w-2/3 mt-20 mx-auto">
      <thead class="text-5xl">
        <tr>
          <th class="text-left">Name</th>
          <th>Quantity</th>
          <th>Remove</th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="order in $store.state.orders"
          :key="order.name"
          class="font-oswald uppercase text-2xl border-b"
        >
          <td class="py-10">{{ order.name }}</td>
          <td class="text-center">{{ order.quantity }}</td>
          <td class="text-center"><button @click="removeItem(order.name)">❌</button></td>
        </tr>
      </tbody>
      <tfoot>
        <tr class="font-oswald font-bold text-2xl bg-gray-100 uppercase">
          <td class="py-10" colspan="1">Total</td>
          <td class="text-center">{{ total }}</td>
        </tr>
      </tfoot>
    </table>
  </div>
</template>

<script>
export default {
  computed: {
    total() {
      let total = 0;
      this.$store.state.orders.forEach((order) => {
        total = total + order.quantity;
      });
      return total;
    },
  },

  methods: {
    removeItem(name) {
      this.$store.commit('removeItem', name);
    },
  },
};
</script>
