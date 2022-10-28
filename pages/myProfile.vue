<script setup>
const inputValue = ref("");
const awesome = ref(false);
const userData = ref({
  name: "Fernando Rodriguez",
  email: "fernando.rodriguez.jm@gmail.com",
  address: "Cosquin 3475",
});

const changeName = () => {
  userData.value.name = inputValue.value;
  inputValue.value = "";
};
const items = ref([{ message: "Foo" }, { message: "Bar" }]);
</script>
<template>
  <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
    <div class="mx-auto max-w-3xl my-10">
      <p class="font-bold text-xl text-center">Perfil de Fernando Rodriguez</p>
      <div class="flex flex-col space-y-5 mt-10">
        <div class="flex flex-row justify-between">
          <p class="text-blue-400 underline">Nombre de usuario:</p>
          <p>{{ userData.name }}</p>
        </div>
        <div class="flex flex-row justify-between">
          <p class="text-blue-400 underline">Email:</p>
          <p>{{ userData.email }}</p>
        </div>
        <div class="flex flex-row justify-between">
          <p class="text-blue-400 underline">Direccion:</p>
          <p>{{ userData.address }}</p>
        </div>
        <div class="flex flex-row space-x-4 items-center">
          <span class="w-60 text-blue-400 underline">Cambiar nombre:</span>
          <input
            v-model="inputValue"
            class="border border-blue-400 rounded-lg shadow-md w-full p-2"
            type="text"
          />
          <button
            @click="changeName()"
            class="rounded-lg shadow-md bg-orange-300 w-40 p-2"
          >
            Aplicar
          </button>
        </div>
        <li v-for="item in items">
          {{ item.message }}
        </li>

        <button @click="awesome = !awesome">Toggle</button>
        <h1 v-if="awesome">Vue is awesome!</h1>
        <h1 v-else>Oh no 😢</h1>
        
      </div>
    </div>
    <p class="text-center font-bold capitalize text-2xl">
      <NuxtLink to="/">
        <span class="cursor-pointer hover:text-blue-500">Volver</span>
      </NuxtLink>
    </p>
  </div>
</template>
