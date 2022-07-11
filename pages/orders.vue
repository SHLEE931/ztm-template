<template>
  <div>
    <div id="header" class="bg-[url('/DeepSkyBlue.jpg')] px-20">
      <div id="menu" class="grid grid-cols-2">
        <div id="menu-left">
          <NuxtLink to="/"
            ><img src="/QorvoLogo4.png" class="w-[200px]" alt="" /></NuxtLink>
        </div>
        <div id="menu-right">
          <ul class="md:grid grid-cols-5 text-lg font-oswald uppercase pt-10">
            <li class="text-white">Hardware</li>
            <li class="text-white">Instrument</li>
            <NuxtLink to="/menu" class="text-white">Components</NuxtLink>
            <NuxtLink to="/cart" class="text-white" >Cart ({{ $store.getters.totalItems }})</NuxtLink>
            <li class="text-white">History</li>
          </ul>
        </div>
      </div>
      <div>
        <div class="py-20">
          <h1
            class="text-6xl text-white text-center font-oswald uppercase pt-24 pb-28"
          >
            History
          </h1>
        </div>
      </div>
    </div>
    <table
      v-for="order in orders"
      :key="order.id"
      class="table-auto w-2/3 mt-20 mx-auto"
    >
      <thead class="text-5xl">
        <tr>
          <td>
            <h1 class="font-oswald uppercase text-2xl pb-10">
              Order ID - {{ order.id }}
            </h1>
          </td>
        </tr>
        <tr>
          <th class="text-left">Name</th>
          <th>Quantity</th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="item in order.data.orders"
          :key="item.name"
          class="font-oswald uppercase text-2xl border-b"
        >
          <td class="py-10">{{ item.name }}</td>
          <td class="text-center">{{ item.quantity }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      orders: [],
    };
  },

  mounted() {
    const dir = '/.netlify/functions/readorders';
    this.$axios.get(dir).then((response) => {
      this.orders = response.data;
    });
  },
};
</script>
