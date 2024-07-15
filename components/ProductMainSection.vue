<template>
  <div class="w-[70%] mx-auto my-4 flex gap-6">
    <div class="w-[75%]">
      <div>
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
              'text-blue-500 border-b-2 border-yellow-500':
                activeTab === 'video',
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
      <div>
        <div class="p-4 border rounded-md">
          <ul class="mt-2 text-gray-500 flex gap-2">
            <li
              v-if="activeTab === 'description'"
              class="flex flex-col gap-2 leading-8"
            >
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
                Provident veniam blanditiis minus amet! Nostrum ipsam
                aspernatur, vitae ea fugit illum quidem at magni, dignissimos
                harum ratione ipsa dicta quaerat. Minus!Lorem ipsum dolor, sit
                amet consectetur adipisicing elit. Provident veniam blanditiis
                minus amet! Nostrum ipsam aspernatur, vitae ea fugit illum
                quidem at magni, dignissimos harum ratione ipsa dicta quaerat.
                Minus!
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
              <i class="fas fa-check-circle text-green-500"></i> The house
              content goes here...
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
              <i class="fas fa-check-circle text-green-500"></i>
              <div class="mb-6">
                <h2 class="text-xl font-semibold mb-2">
                  Frequently Asked Questions
                </h2>
                <div class="space-y-4">
                  <div>
                    <p class="font-semibold text-md">
                      Do I need to book a visit at Champagne Charles Pougeoise
                      in advance?
                    </p>
                    <p>
                      We advise you to book in advance because availabilities
                      are limited. However, of course you can also make a last
                      minute booking.
                    </p>
                  </div>
                  <div>
                    <p class="font-semibold text-md">
                      Do I need to pay online?
                    </p>
                    <p>
                      No, you will pay at the champagne house (by cash, bank
                      card, credit card).
                    </p>
                  </div>
                  <div>
                    <p class="font-semibold text-lg">
                      Can I cancel my booking?
                    </p>
                    <p>
                      Yes, you can cancel your booking without any charges 24
                      hours before your visit takes place. * Please note that
                      Champagne Charles Pougeoise will charge you the full
                      amount of the booking in case of no-show / no notification
                      of cancellation or no timely cancellation.
                    </p>
                  </div>
                  <div>
                    <p class="font-semibold text-lg">
                      How can I cancel my booking?
                    </p>
                    <p>
                      You can login into your own account on the website and
                      cancel your booking without any costs 24 hours before your
                      visit. Of course we will be happy to assist you with your
                      questions by sending us an email to:
                      <a
                        href="mailto:info@champagne-booking.com"
                        class="text-blue-600 underline"
                        >info@champagne-booking.com</a
                      >
                    </p>
                  </div>
                </div>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <div class="w-25% flex flex-col gap-4">
      <div class="border p-4 rounded-md flex flex-col gap-2">
        <h1 class="font-semibold">Why Champagne-Booking.com?</h1>
        <p>
          <span class="text-green-500 mr-2"
            ><font-awesome icon="fa-check" /></span
          >Pay upon arrival
        </p>
        <p>
          <span class="text-green-500 mr-2"
            ><font-awesome icon="fa-check" /></span
          >No booking fee
        </p>
        <p>
          <span class="text-green-500 mr-2"
            ><font-awesome icon="fa-check" /></span
          >Excellent customer service
        </p>
        <p>
          <span class="text-green-500 mr-2"
            ><font-awesome icon="fa-check" /></span
          >Simple and fast
        </p>
      </div>
      <div class="border p-4 rounded-md flex flex-col gap-2">
        <h1 class="font-semibold">Popular Champagne Houses</h1>

        <div class="flex justify-between gap-2 items-center border-b pb-2">
          <div>
            <p class="font-bold">Champagne Mumm</p>
            <p class="text-sm text-gray-500">1114 reviews</p>
          </div>

          <img
            src="https://images.pexels.com/photos/2454095/pexels-photo-2454095.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2"
            alt="champagne house"
            class="w-14 h-14 rounded-md"
          />
        </div>
        <div class="flex justify-between gap-2 items-center border-b pb-2">
          <div>
            <p class="font-bold">Champagne Mercier</p>
            <p class="text-sm text-gray-500">1114 reviews</p>
          </div>

          <img
            src="https://images.pexels.com/photos/2454095/pexels-photo-2454095.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2"
            alt="champagne house"
            class="w-14 h-14 rounded-md"
          />
        </div>
        <div class="flex justify-between gap-2 items-center border-b pb-2">
          <div>
            <p class="font-bold">Champagne Pommery</p>
            <p class="text-sm text-gray-500">1114 reviews</p>
          </div>

          <img
            src="https://images.pexels.com/photos/2995339/pexels-photo-2995339.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2"
            alt="champagne house"
            class="w-14 h-14 rounded-md"
          />
        </div>
        <div class="flex justify-between gap-2 items-center border-b pb-2">
          <div>
            <p class="font-bold">Champagne Taittinger</p>
            <p class="text-sm text-gray-500">1114 reviews</p>
          </div>

          <img
            src="https://images.pexels.com/photos/2454095/pexels-photo-2454095.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2"
            alt="champagne house"
            class="w-14 h-14 rounded-md"
          />
        </div>
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
