<script setup>
import VueDatePicker from "@vuepic/vue-datepicker";
import "@vuepic/vue-datepicker/dist/main.css";

const date = ref();
const openConfirm = ref(true);
const openSide = ref(false);
</script>
<template>
  <NavsThemeSwitcher class="pl-40" />
  <ModalsSidebar v-model="openSide" :autoClose="false">
    <template #Heading>
      <div class="flex justify-between">
        <h1>Title</h1>
        <h1>Heading</h1>
      </div>
    </template>
    <template #Content
      ><div
        class="flex min-h-full flex-1 flex-col justify-center px-6 py-12 lg:px-8"
      >
        <div class="sm:mx-auto sm:w-full sm:max-w-sm">
          <Icon
            name="iconamoon:check"
            width="55"
            height="55"
            class="w-full flex justify-center"
          />
          <h2
            class="mt-10 text-center text-2xl font-bold leading-9 tracking-tight text-gray-900"
          >
            Modal Component
          </h2>
        </div>
      </div>
    </template>
  </ModalsSidebar>
  <button @click="openSide = true">Open sidebar</button>
  <ModalsModal v-model="openConfirm" :autoClose="false">
    <template #Heading>
      <div class="flex justify-between items-center w-full text-gray-600">
        <Icon name="simple-line-icons:check" width="25" height="25" />
        <h1>Title</h1>
        <h1></h1>
      </div>
    </template>
    <template #content>
      <div
        class="flex min-h-full flex-1 flex-col justify-center px-6 py-12 lg:px-8"
      >
        <div class="sm:mx-auto sm:w-full sm:max-w-sm">
          <Icon
            name="iconamoon:check"
            width="55"
            height="55"
            class="w-full flex justify-center"
          />
          <h2
            class="mt-10 text-center text-2xl font-bold leading-9 tracking-tight text-gray-900"
          >
            Modal Component
          </h2>
        </div>
      </div>
    </template>
  </ModalsModal>

  <VueDatePicker v-model="date"></VueDatePicker>
  <HTextfield name="testfield" class="w-60" />
  
</template>
