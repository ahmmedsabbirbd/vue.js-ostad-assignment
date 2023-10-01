<script setup>
// import { useAuth } from "@/stores/auth";
import { useAuth } from "../stores/auth";

const auth = useAuth();
</script>

<template>
  <div
    class="bg-img bg-center bg-cover bg-no-repeat flex justify-center items-center p-4 sm:ml-64"
  >
    <div
      class="p-5 md:p-10 text-center bg-white bg-opacity-60 border-[#00DCBD] border-2 border-dashed rounded-lg"
    >
      <h1 class="text-center text-4xl font-bold">Welcome To Admin Panel</h1>
      <br />
      <h1 class="font-bold">
        Your Email is :
        <span class="font-normal italic">{{ auth.user.newUserEmail }}</span>
      </h1>
    </div>
  </div>
</template>

<style scoped>
.bg-img {
  background: rgb(184,142,15);
background: linear-gradient(90deg, rgba(184,142,15,0.9651216656974192) 0%, rgba(121,9,116,1) 48%, rgba(255,40,0,1) 100%); 
min-height: 100vh;
}

</style>
