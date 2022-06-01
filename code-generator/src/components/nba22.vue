<template>
<form class="space-y-6" action="#" method="POST">
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
      >
        <span class="font-normal block truncate"> 10000 </span>

      </li>
      <li
          class="text-gray-900 cursor-default select-none relative py-2 pl-3 pr-9"
          role="option"
      >
        <span class="font-normal block truncate"> 100000 </span>


      </li>
      <li
          class="text-gray-900 cursor-default select-none relative py-2 pl-3 pr-9"
          role="option"
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
      >
        <span class="font-normal block truncate"> 5000000 </span>

      </li>
      <li
          class="text-gray-900 cursor-default select-none relative py-2 pl-3 pr-9"
          role="option"
      >
        <span class="font-normal block truncate"> 50000000 </span>


      </li>
      <li
          class="text-gray-900 cursor-default select-none relative py-2 pl-3 pr-9"
          role="option"
      >
        <span class="font-normal block truncate"> 500000000 </span>
      </li>


    </ul>
  </div>
</div>

<div>
  <button
      @click.prevent="step = 2"
      class="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white b-primary hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
  >
    GENERATE
  </button>
</div>
</form>
</template><