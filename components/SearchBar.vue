<template>
  <div
    class="w-full mx-auto relative flex flex-col justify-center items-center"
  >
    <form
      class="lg:w-[70%] md:w-full w-[90%] p-2 flex flex-col lg:flex-row md:flex-col gap-2 justify-between items-center bg-yellow-500 rounded-md absolute -top-10"
    >
      <!-- Where do you want to go? -->
      <div
        class="flex flex-col flex-grow bg-white rounded-md p-2 w-full h-full"
      >
        <label
          for="destination"
          class="block text-sm font-medium text-gray-700 w-full h-full text-nowrap ml-2"
          >Where do you want to go?</label
        >
        <input
          type="text"
          id="destination"
          name="destination"
          placeholder="Champagne House or destination "
          class="mt-1 block p-2 w-full rounded-md shadow-sm"
        />
      </div>

      <!-- When? -->
      <div class="flex flex-col flex-grow bg-white rounded-md p-2 w-full">
        <label for="date" class="block text-sm font-medium text-gray-700 ml-2"
          >When?</label
        >
        <input
          type="date"
          id="date"
          name="date"
          class="mt-1 block w-full p-2 rounded-md shadow-sm text-gray-400"
          :value="todayDate"
        />
      </div>

      <!-- How many persons? -->
      <div class="flex flex-col flex-grow bg-white rounded-md p-2 w-full">
        <label for="persons" class="block text-sm font-medium text-gray-700 ml-2"
          >How many persons?</label
        >
        <input
          type="text"
          id="persons"
          name="persons"
          placeholder="2 adults"
          class="mt-1 block w-full p-2 rounded-md shadow-sm"
        />
      </div>

      <!-- Search button -->
      <div class="flex flex-grow w-full h-full">
        <button
          type="submit"
          class="w-full h-full bg-red-700 text-white lg:py-7 py-2 px-4 rounded-md shadow-sm hover:bg-red-800 focus:outline-none text-center items-center justify-center flex"
        >
          Search
        </button>
      </div>
    </form>
  </div>
</template>

<script setup>
const formatDate = (date) => {
  const d = new Date(date);
  const month = ("0" + (d.getMonth() + 1)).slice(-2);
  const day = ("0" + d.getDate()).slice(-2);
  const year = d.getFullYear();
  return `${year}-${month}-${day}`;
};

// Compute today's date
const todayDate = ref(formatDate(new Date()));
</script>

<style lang="scss" scoped></style>
