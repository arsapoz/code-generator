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
       <Nba22  v-if="step === 1"/>
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
import Nba22 from "./components/nba22";

export default {
  components: {Nba22},
  setup () {
    const step = ref (1);
    const dropdown = ref(false);
    const dropdown2 = ref(false);
    const dropdownValue = ref(1000);
    const dropdown2Value = ref(500000);

    const stepperStyle = computed(() => {
      if (this.step === 1){
        return 'width:25%'
      }else if (this.step === 2){
        return 'width:50%'
      }else{
        return 'width:75%'
      }
    })
    onMounted(() => {
      let self = this
      window.addEventListener('click', function(e) {
        // close dropdown when clicked outside
        if (!self.$el.contains(e.target)) {
          self.dropdown = false
          self.dropdown2 = false
        }
      })
    })

    return {
      dropdown,
      dropdown2,
      dropdownValue,
      dropdown2Value,
      step
    };
  }
}
</script>