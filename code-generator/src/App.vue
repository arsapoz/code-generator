<template>
  <div
      class="min-h-full flex flex-col justify-center py-16 sm:px-6 lg:px-8 bg-gray-900"
  >
    <div class="sm:mx-auto sm:w-full sm:max-w-md px-2">
      <div>
        <h4 class="sr-only">Status</h4>
        <p class="text-sm font-medium text-gray-900">
          Migrating MySQL database...
        </p>
        <div class="mt-6" aria-hidden="true">
          <div class="bg-gray-200 rounded-full overflow-hidden">
            <div class="h-2 b-primary rounded-full" :style="stepperStyle"></div>
          </div>
          <div
              class="hidden sm:grid grid-cols-4 text-sm font-medium text-gray-600 mt-6"
          >
            <div class="c-primary">Chose amount</div>
            <div class="text-right">Connecting</div>
            <div class="text-center">Generating</div>
            <div class="text-center">Completed</div>
          </div>
        </div>
      </div>

      <img class="p-10" src="/logo.svg" alt="My gift card station" />
    </div>

    <div class="mt-8 sm:mx-auto sm:w-full sm:max-w-md">
      <div class=" px-4 shadow sm:rounded-lg sm:px-10">
<!--       <Nba22  v-if="step === 1"/>-->

          <form class="space-y-6" action="#" method="POST" v-if="step === 1">
            <div>
              <label
                  id="listbox-label"
                  class="block text-sm font-medium text-white"
              >
                Stars amount
              </label>
              <div class="mt-1 relative">
                <button
                    @click="dropdown = !dropdown"
                    type="button"
                    class="bg-white relative w-full border border-gray-300 rounded-md shadow-sm pl-3 pr-10 py-2 text-left cursor-default focus:outline-none focus:ring-1 focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                    aria-haspopup="listbox"
                    aria-expanded="true"
                    aria-labelledby="listbox-label"
                >
                  <span class="block truncate"> {{ dropdownValue }} </span>
                  <span
                      class="absolute inset-y-0 right-0 flex items-center pr-2 pointer-events-none"
                  >
                  <svg
                      class="h-5 w-5 text-gray-400"
                      xmlns="http://www.w3.org/2000/svg"
                      viewBox="0 0 20 20"
                      fill="currentColor"
                      aria-hidden="true"
                  >
                    <path
                        fill-rule="evenodd"
                        d="M10 3a1 1 0 01.707.293l3 3a1 1 0 01-1.414 1.414L10 5.414 7.707 7.707a1 1 0 01-1.414-1.414l3-3A1 1 0 0110 3zm-3.707 9.293a1 1 0 011.414 0L10 14.586l2.293-2.293a1 1 0 011.414 1.414l-3 3a1 1 0 01-1.414 0l-3-3a1 1 0 010-1.414z"
                        clip-rule="evenodd"
                    />
                  </svg>
                </span>
                </button>


                <ul v-if="dropdown"
                    class="absolute z-10 mt-1 w-full bg-white shadow-lg max-h-60 rounded-md py-1 text-base ring-1 ring-black ring-opacity-5 overflow-auto focus:outline-none sm:text-sm"
                    tabindex="-1"
                    role="listbox"
                >
                  <li
                      class="text-gray-900 cursor-default select-none relative py-2 pl-3 pr-9"
                      role="option"
                      @click="dropdownValue = 1000; dropdown = false"
                  >
                    <span class="font-normal block truncate"> 1000 </span>

                  </li>
                  <li
                      class="text-gray-900 cursor-default select-none relative py-2 pl-3 pr-9"
                      role="option"
                      @click="dropdownValue = 10000; dropdown = false"
                  >
                    <span class="font-normal block truncate"> 10000 </span>


                  </li>
                  <li
                      class="text-gray-900 cursor-default select-none relative py-2 pl-3 pr-9"
                      role="option"
                      @click="dropdownValue = 100000; dropdown = false"
                  >
                    <span class="font-normal block truncate"> 100000 </span>
                  </li>
                </ul>
              </div>
            </div>

            <div>
              <label
                  class="block text-sm font-medium text-white"
              >
                Points amount
              </label>
              <div class="mt-1 relative">
                <button

                    @click="dropdown2 = !dropdown2"
                    type="button"
                    class="bg-white relative w-full border border-gray-300 rounded-md shadow-sm pl-3 pr-10 py-2 text-left cursor-default focus:outline-none focus:ring-1 focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                    aria-haspopup="listbox"
                    aria-expanded="true"
                    aria-labelledby="listbox-label"
                >
                  <span class="block truncate"> {{ dropdown2Value }} </span>
                  <span
                      class="absolute inset-y-0 right-0 flex items-center pr-2 pointer-events-none"
                  >
                  <!-- Heroicon name: solid/selector -->
                  <svg
                      class="h-5 w-5 text-gray-400"
                      xmlns="http://www.w3.org/2000/svg"
                      viewBox="0 0 20 20"
                      fill="currentColor"
                      aria-hidden="true"
                  >
                    <path
                        fill-rule="evenodd"
                        d="M10 3a1 1 0 01.707.293l3 3a1 1 0 01-1.414 1.414L10 5.414 7.707 7.707a1 1 0 01-1.414-1.414l3-3A1 1 0 0110 3zm-3.707 9.293a1 1 0 011.414 0L10 14.586l2.293-2.293a1 1 0 011.414 1.414l-3 3a1 1 0 01-1.414 0l-3-3a1 1 0 010-1.414z"
                        clip-rule="evenodd"
                    />
                  </svg>
                </span>
                </button>
                <ul
                    v-if="dropdown2"
                    class="absolute z-10 mt-1 w-full bg-white shadow-lg max-h-60 rounded-md py-1 text-base ring-1 ring-black ring-opacity-5 overflow-auto focus:outline-none sm:text-sm"
                    tabindex="-1"
                    role="listbox"
                >

                  <li
                      class="text-gray-900 cursor-default select-none relative py-2 pl-3 pr-9"
                      role="option"
                      @click="dropdown2Value = 500000; dropdown2 = false"
                  >
                    <span class="font-normal block truncate"> 500000 </span>

                  </li>
                  <li
                      class="text-gray-900 cursor-default select-none relative py-2 pl-3 pr-9"
                      role="option"
                      @click="dropdown2Value = 50000000; dropdown2 = false"
                  >
                    <span class="font-normal block truncate"> 50000000 </span>


                  </li>
                  <li
                      class="text-gray-900 cursor-default select-none relative py-2 pl-3 pr-9"
                      role="option"
                      @click="dropdown2Value = 500000000; dropdown2 = false"
                  >
                    <span class="font-normal block truncate"> 500000000 </span>
                  </li>


                </ul>
              </div>
            </div>
          </form>
        <div v-if="step === 2" class="flex flex-col">
          <img class="p-16 w-full" src="/loader.svg" alt="Loading"  />
          <div class="text-white">
          <div>Connecting to NBA server</div>
          <div>
          Connecting to sql database...
          </div>
          <div>Closing server handles..</div>
          <div>
            Searching databse for unused codes...
            (Seraching trought codes)
          </div>

          <div>
            (RANDOM CODE) - XXXX
            <p>Success!</p>
          </div>
          </div>
        </div>
        <div class="mt-5">
          <button
              v-if="step === 1"
              @click.prevent="step = 2"
              class="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white b-primary hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
          >
            GENERATE
          </button>
        </div>
      </div>
      <div class="flex flex-col justify-center items-center text-center mt-6">
        <div class="mb-6">
          <a href="#">Contact Us</a> | <a href="#">Terms of service</a> |
          <a href="#">Privacy policy</a>
        </div>
        <p class="text-white">
          All trademarks, service marks, trade names, trade dress, product names
          and logos appearing on the site are the property of their respective
          owners.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, onMounted, computed } from 'vue'
import  Nba22  from '@/components/nba22.vue'

export default {
  components: {
    Nba22
  },
  setup () {
    let step = ref (1);
    let dropdown = ref(false);
    let dropdown2 = ref(false);
    let dropdownValue = ref(1000);
    let dropdown2Value = ref(500000);

    const stepperStyle = computed(() => {
      if (step.value === 1){
        return 'width:25%'
      }else if (step.value === 2){
        return 'width:50%'
      }else{
        return 'width:75%'
      }
    })
    onMounted(() => {
      window.addEventListener('click', function(e) {
        // close dropdown when clicked outside
        if (!$el.contains(e.target)) {
          dropdown = false
          dropdown2 = false
        }
      })
    })
    return {
      dropdown,
      dropdown2,
      dropdownValue,
      dropdown2Value,
      step,
      stepperStyle
    };
  }
}
</script>