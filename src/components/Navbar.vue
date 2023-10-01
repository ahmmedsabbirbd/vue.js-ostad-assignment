<script setup>
import router from "../router";
import { useAuth } from "../stores/auth";
// import router from "@/router";
// import { useAuth } from "@/stores/auth.js";
import { ElMessage, ElNotification } from "element-plus";

const auth = useAuth();
function logOut() {
  const success = auth.logout();
  if (success) {
    router.push({ name: "login" });
    ElNotification({
      title: "Success",
      message: "You have Successfully Logged Out",
      type: "success",
      position: "top-right",
      duration: 2000,
    });
  } else {
    ElMessage({
      type: "error",
      message: "Something went wrong",
    });
  }
}
</script>

<template>
  <nav class="bg-blue-400 sticky top-0 shadow-lg">
    <div
      class="flex flex-wrap justify-between items-center mx-auto max-w-screen-xl p-4"
    >
      <RouterLink :to="{ name: 'dashboard' }" class="flex items-center">
        <img src="https://cdn.ostad.app/public/upload/2022-11-27T06-52-05.802Z-logo ostad.png" alt="">
      </RouterLink>

      <div class="flex items-center">
        <button @click.prevent="logOut()" class="text-lg font-bold text-black">
          Log Out
        </button>
      </div>
    </div>
  </nav>
</template>

<style scoped></style>
