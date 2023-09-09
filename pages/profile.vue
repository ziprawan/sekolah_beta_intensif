<template>
  <main>
    <div class="w-full p-5 sm:p-10 flex flex-col bg-white shadow-md rounded-2xl relative">
      <div class="block sm:hidden text-3xl font-semibold mb-3 relative">
        Profile
      </div>
      <div class="relative overflow-hidden w-36 h-36 rounded-full m-auto bg-transparent flex justify-center items-center">
        <img src="../assets/default.webp" />
      </div>
      <div class="px-4 py-2 mt-2 bg-gray-100 rounded-lg">
        <p class="font-semibold">Name</p>
        <p>Aziz Ridhwan Pratama</p>
      </div>
      <div class="px-4 py-2 mt-2 bg-gray-100 rounded-lg">
        <p class="font-semibold">Username</p>
        <p>ridhwan_aziz</p>
      </div>
      <button class="py-3 px-4 mt-3 bg-gray-100 hover:bg-slate-950 hover:text-white transition w-fit rounded-lg font-semibold flex items-center gap-1">
        Log Out
      </button>
    </div>
  </main>
</template>