<template>
  <div class="shadow">
    <nav class="bg-gray-100">
      <div class="max-w-7xl mx-auto px-4 py-1 sm:px-6 lg:px-8">
        <div class="flex items-center justify-between">
          <div class="flex items-center w-full">
            <div class="flex-shrink-0">
              <img
                class="h-16 w-20"
                src="https://fygsolutions.com/wp-content/uploads/2021/07/cropped-logo-final.png"
                alt="Workflow"
              />
            </div>
            <!-- <div class="flex">
              <div class="ml-10 flex items-baseline space-x-4">
                <router-link
                  :to="{ name: 'LoadData' }"
                  class="px-3 py-2 rounded-md text-sm font-medium text-gray-800 hover:text-gray-700"
                >
                  Data
                </router-link>
              </div>
            </div> -->
            <div class="flex">
              <div class="ml-10 flex items-baseline space-x-4">
                <router-link
                  :to="{ name: 'Home' }"
                  class="px-3 py-2 rounded-md text-sm font-medium text-gray-800 hover:text-gray-700"
                >
                  Sorteo
                </router-link>
              </div>
            </div>
            <div class="flex">
              <div class="ml-10 flex items-baseline space-x-4">
                <router-link
                  :to="{ name: 'Colaboradores' }"
                  class="px-3 py-2 rounded-md text-sm font-medium text-gray-800 hover:text-gray-700"
                >
                  Premios
                </router-link>
              </div>
            </div>
            <div class="flex justify-self-end">
              <div class="ml-10 flex items-baseline space-x-4">
                <a
                  @click="logout"
                  class="px-3 py-2 rounded-md text-sm font-medium text-gray-800 hover:text-gray-700 cursor-pointer"
                >
                  Logout
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!--
      Mobile menu, toggle classes based on menu state.
 
      Open: "block", closed: "hidden"
    -->
      <div class="hidden md:hidden">
        <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
          <a
            href="#"
            class="block px-3 py-2 rounded-md text-base font-medium text-white bg-gray-900"
            >Inicio</a
          >
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
import firebase from "firebase";

export default {
  name: "Navbar",
  props: {
    msg: String
  },
  methods: {
    logout() {
      firebase
        .auth()
        .signOut()
        .then(() => {
          this.$router.replace("login");
        });
    }
  }
};
</script>
