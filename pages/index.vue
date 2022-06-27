<template>
<div>
  <div id="header" class="bg-[url('/DeepSkyBlue.jpg')] px-20 px-5">
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
</div>
</template>
