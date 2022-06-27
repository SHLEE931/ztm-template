<template>
      <div class="text-center">
        <img :src="item.image" alt="" class="border border-gray p-5 px-10" />
        <h2 class="font-oswald uppercase mt-5 text-2xl">{{ item.name }}</h2>
        <p class="font-light text-gray-500 my-2 mt-5 mb-5">{{ item.description }}</p>
        <button class="mt-5 mb-5 button font-oswald uppercase border py-2 px-3 rounded rounded-lg bg-amber-800 text-yellow-400 text-x1" @click="addItem">Add to cart</button>
      </div>
</template>

<script>
export default {
  props: ['item'],
  methods: {
    addItem() {
      this.$store.commit('addItem', this.item);
    },
  },
};
</script>
