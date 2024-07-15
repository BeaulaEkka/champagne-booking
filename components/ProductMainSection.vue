<template>
  <div class="w-[70%] mx-auto my-4 flex flex-col gap-6">
    <div class="w-[80%]">
      <ul class="flex gap-4 justify-between border-b-2 pb-4">
        <li
          :class="{
            'text-blue-500 border-b-2 border-yellow-500':
              activeTab === 'description',
          }"
          @click="setActiveTab('description')"
          class="hover:text-blue-500 cursor-pointer"
        >
          Description
        </li>
        <li
          :class="{
            'text-blue-500 border-b-2 border-yellow-500':
              activeTab === 'the-house',
          }"
          @click="setActiveTab('the-house')"
          class="hover:text-blue-500 cursor-pointer"
        >
          The house
        </li>
        <li
          :class="{
            'text-blue-500 border-b-2 border-yellow-500':
              activeTab === 'photos',
          }"
          @click="setActiveTab('photos')"
          class="hover:text-blue-500 cursor-pointer"
        >
          Photos
        </li>
        <li
          :class="{
            'text-blue-500 border-b-2 border-yellow-500': activeTab === 'video',
          }"
          @click="setActiveTab('video')"
          class="hover:text-blue-500 cursor-pointer"
        >
          Video
        </li>
        <li
          :class="{
            'text-blue-500 border-b-2 border-yellow-500': activeTab === 'faq',
          }"
          @click="setActiveTab('faq')"
          class="hover:text-blue-500 cursor-pointer"
        >
          Frequently asked questions
        </li>
      </ul>
    </div>
    <div class="w-[80%]">
      <div class="p-4 border rounded-md">
        <ul class="mt-2 text-gray-500 flex gap-2">
          <li
            v-if="activeTab === 'description'"
            class="flex flex-col gap-2 leading-8"
          >
            <h1></h1>
            <h1 class="font-bold text-lg">Title content goes here</h1>
            <p>
              Lorem ipsum dolor sit amet consectetur, adipisicing elit.
              Aspernatur sint, consequatur repellendus dolore perspiciatis
              facilis ea eligendi voluptates id fugiat, iure voluptatem!
              Dignissimos quos, animi neque a est atque laboriosam.Lorem ipsum
              dolor sit amet consectetur, adipisicing elit. Aspernatur sint,
              consequatur repellendus dolore perspiciatis facilis ea eligendi
              voluptates id fugiat, iure voluptatem! Dignissimos quos, animi
              neque a est atque laboriosam.
            </p>

            <h1 class="font-bold text-lg">Title content goes here</h1>
            <p>
              Lorem ipsum dolor, sit amet consectetur adipisicing elit.
              Provident veniam blanditiis minus amet! Nostrum ipsam aspernatur,
              vitae ea fugit illum quidem at magni, dignissimos harum ratione
              ipsa dicta quaerat. Minus!Lorem ipsum dolor, sit amet consectetur
              adipisicing elit. Provident veniam blanditiis minus amet! Nostrum
              ipsam aspernatur, vitae ea fugit illum quidem at magni,
              dignissimos harum ratione ipsa dicta quaerat. Minus!
            </p>

            <h1 class="font-bold text-lg">Title content goes here</h1>
            <p>
              Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ad,
              tempore! Repudiandae atque dolores vitae blanditiis esse ipsam
              explicabo iste nam repellendus. Ipsa dolorem, similique pariatur
              aspernatur itaque excepturi nobis delectus!
            </p>
          </li>
          <li v-else-if="activeTab === 'the-house'">
            <i class="fas fa-check-circle text-green-500"></i> The house content
            goes here...
          </li>
          <li v-else-if="activeTab === 'photos'">
            <i class="fas fa-check-circle text-green-500"></i> Photos content
            goes here...
          </li>
          <li v-else-if="activeTab === 'video'">
            <i class="fas fa-check-circle text-green-500"></i> Video content
            goes here...
          </li>
          <li v-else-if="activeTab === 'faq'">
            <i class="fas fa-check-circle text-green-500"></i> Frequently asked
            questions content goes here...
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const activeTab = ref("description");

const setActiveTab = (tab) => {
  activeTab.value = tab;
};
</script>

<style scoped>
@media (min-width: 640px) {
  .grid-cols-2 {
    grid-template-columns: 70% 30%;
  }
}
</style>
