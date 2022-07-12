<template>
<div>
  <div id="header" class="bg-[url('/DeepSkyBlue.jpg')] px-20 px-5">
    <div id="menu" class="grid grid-cols-2">
      <div id="menu-left">
        <NuxtLink to="/"><img src="/QorvoLogo4.png" class="w-[200px]" alt="" /></NuxtLink>
      </div>
      <div id="menu-right">
          <ul class="md:grid grid-cols-2 text-lg font-oswald uppercase pt-10">
            <button @click="isOpen = !isOpen" class="text-white">Menu</button>
            <!--<button class="px-4 py-2 text-white">Cart</button>-->
            <button class="px-4 py-2 text-white"><NuxtLink to="/cart" class="text-white">Cart ({{ $store.getters.totalItems }})</NuxtLink></button>
            <!--<NuxtLink to="/cart" class="text-white">Cart ({{ $store.getters.totalItems }})</NuxtLink>-->
            <div v-if="isOpen" class="md:grid grid-row-2 text-lg font-oswald uppercase text-center bg-white rounded-lg ">
              <a href="#" class="block px-4 py-2 hover:bg-gray-500 hover:text-white"><NuxtLink to="/coupler">Component</NuxtLink></a>
              <a href="#" class="block px-4 py-2 hover:bg-gray-500 hover:text-white"><NuxtLink to="/coupler">Hardware</NuxtLink></a>
            </div>
            <!--<ul v-if="isOpen" class="md:grid grid-row-2 text-lg font-oswald uppercase text-center bg-white rounded-lg ">
              <il><a href="#" class="block px-4 py-2 hover:bg-gray-500 hover:text-white">Component</a></il>
              <il><a href="#" class="block px-4 py-2 hover:bg-gray-500 hover:text-white">Hardware</a></il>
            </ul>-->
            <!--<button class="text-white">Cart</button>-->
            <!--<div v-if="isOpen" class="bg-white rounded-lg py-2 items-enter">-->
            <!--</div>-->
            <!--<li class="text-white">Hardware</li>-->
            <!--<li class="text-white">Instrument</li>-->
            <!--<NuxtLink to="/menu" class="text-white">Components</NuxtLink>-->
            <!--<NuxtLink to="/cart" class="text-white">Cart ({{ $store.getters.totalItems }})</NuxtLink>-->
          </ul>
      </div>
    </div>
    <div class="grid grid-cols-2 pb-20 pt-10 text-center">
      <img src="/Hardware.jpg" class="pr-8 pb-5 mt-10 pt-20" alt="" />
      <div class="py-20">
        <h1 class="pt-5 text-white font-lilita uppercase md:text-6xl lg:text-7xl xl:text-9xl">
          Inventory
        </h1>
        <h2 class="text-white font-lilita uppercase my-5 md:text-3xl lg:text-5xl xl:text-7xl">
          Management System
        </h2>
        <p class="text-white font-roboto font-light">
          Keep track on all the instrument, hardware and components available at
          Malaysia Qorvo.
        </p>
      </div>
    </div>
  </div>
  <div id="Menu">
    <h2 class="text-center text-blue-400 md:text-3xl lg:text-5xl xl:text-7xl">Menu</h2>
  </div>
  <table class="table-auto w-2/3 mt-20 mx-auto border border-black-500 mb-10">
  <thead>
    <tr>
      <th class="text-left">Product</th>
      <th class="text-left">Component</th>
      <th class="text-left">Hardware</th>
      <th class="text-left">LoadBoard</th>
    </tr>
  </thead>
  <tbody class="border border-black-500">
    <tr class="border border-black-500">
      <td><NuxtLink to="/filter">Filter</NuxtLink></td>
      <td>Capacitor</td>
      <td>Dsub 20</td>
    </tr>
    <tr class="border border-black-500">
      <td><NuxtLink to="/attenuator">Attenuator</NuxtLink></td>
      <td>Inductor</td>
      <td>VHDCI</td>
    </tr>
    <tr class="border border-black-500">
      <td><NuxtLink to="/coupler">Coupler</NuxtLink></td>
      <td>Resistor</td>
      <td>Dsub 60</td>
    </tr>
    <tr class="border border-black-500">
      <td><NuxtLink to="/thru">Thru</NuxtLink></td>
      <td>Capacitor</td>
      <td>N/A</td>
    </tr>
    <tr class="border border-black-500">
      <td><NuxtLink to="/Terminator">Terminator</NuxtLink></td>
      <td>N/A</td>
      <td>N/A</td>
    </tr>
    <tr class="border border-black-500">
      <td><NuxtLink to="/adapter">Adapter</NuxtLink></td>
      <td>N/A</td>
      <td>N/A</td>
    </tr>
    <tr class="border border-black-500">
      <td><NuxtLink to="/biastee">Bias Tee</NuxtLink></td>
      <td>N/A</td>
      <td>N/A</td>
    </tr>
    <tr class="border border-black-500">
      <td><NuxtLink to="/dcblock">DC Block</NuxtLink></td>
      <td>N/A</td>
      <td>N/A</td>
    </tr>
    <tr class="border border-black-500">
      <td><NuxtLink to="/limiter">Limiter</NuxtLink></td>
      <td>N/A</td>
      <td>N/A</td>
    </tr>
    <tr class="border border-black-500">
      <td>Impedance matching pad</td>
      <td>N/A</td>
      <td>N/A</td>
    </tr>
    <tr class="border border-black-500">
      <td><NuxtLink to="/rfchokes">RF Chokes</NuxtLink></td>
      <td>N/A</td>
      <td>N/A</td>
    </tr>
  </tbody>
</table>
</div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false
    }
  }
}
</script>
