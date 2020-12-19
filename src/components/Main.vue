<template>
  <main class="-mt-32">
    <div class="max-w-7xl mx-auto pb-12 px-4 sm:px-6 lg:px-8">
      <div class="bg-white rounded-lg shadow px-5 py-6 sm:px-6">
        <div class="rounded-lg h-96">
          <div class="mt-4 mx-12 w-full">
            <div class="py-8 px-4 sm:px-10">
              <form class="space-y-6" action="#" method="POST">
                <div class="flex items-center">
                  <label
                    for="name"
                    class="block font-medium text-gray-700 mr-3 w-48"
                  >
                    Team/Person Name
                  </label>
                  <div class="mt-1">
                    <input
                      v-model="name"
                      type="text"
                      class="appearance-none block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm placeholder-gray-400 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                      :class="{ 'border-red-500': errors.name }"
                    />
                    <div class="text-red-500 text-sm">{{ errors.name }}</div>
                  </div>
                  <button
                    @click="addName"
                    type="button"
                    class="mx-3 text-green-500 hover:bg-purple-500 hover:text-white rounded-full focus:outline-none p-0.5"
                  >
                    <svg
                      class="w-7 h-7"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                      xmlns="http://www.w3.org/2000/svg"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M10 5a1 1 0 011 1v3h3a1 1 0 110 2h-3v3a1 1 0 11-2 0v-3H6a1 1 0 110-2h3V6a1 1 0 011-1z"
                        clip-rule="evenodd"
                      ></path>
                    </svg>
                  </button>
                </div>
                <div class="flex items-center">
                  <label class="block font-medium text-gray-700 mr-3 w-48">
                    Person
                  </label>
                  <input
                    v-for="name of names"
                    :key="name"
                    :value="name"
                    class="flex md:flex-col px-3 py-2 mb-4 text-lg font-semibold focus:outline-none"
                  />
                </div>
                <div class="flex items-center">
                  <label class="block font-medium text-gray-700 mr-3 w-48">
                    Choices
                  </label>
                  <div class="mt-1">
                    <input
                      name="text"
                      class="appearance-none block px-3 py-2 border border-gray-300 rounded-md shadow-sm placeholder-gray-400 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                    />
                  </div>
                  <button
                    type="button"
                    class="mx-3 text-green-500 hover:bg-purple-500 hover:text-white rounded-full focus:outline-none p-0.5"
                  >
                    <svg
                      class="w-7 h-7"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                      xmlns="http://www.w3.org/2000/svg"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M10 5a1 1 0 011 1v3h3a1 1 0 110 2h-3v3a1 1 0 11-2 0v-3H6a1 1 0 110-2h3V6a1 1 0 011-1z"
                        clip-rule="evenodd"
                      ></path>
                    </svg>
                  </button>
                </div>
                <button
                  href="#"
                  class="px-8 py-2 border border-transparent text-base font-medium rounded-md text-white bg-pink-600 hover:bg-pink-700 focus:outline-none md:text-lg"
                >
                  Start
                </button>
              </form>
            </div>
          </div>
        </div>
      </div>
      <!-- /End replace -->
    </div>
  </main>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: "",
      names: [],
      errors: {},
    };
  },

  methods: {
    addName: function() {
      this.errors = {};
      if (this.name === "") {
        this.errors.name = "Name is required";
        return;
      }
      this.names.push(this.name);
      this.name = null;
    },
  },
};
</script>
