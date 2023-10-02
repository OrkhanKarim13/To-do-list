<script>
export default {
  data() {
    return {
      inputValue: null,
      appendedText: [

      ],
    };
  },
  methods: {
    addTask() {
      if (this.inputValue != null) {
        this.appendedText.push(this.inputValue)
        this.inputValue = null
      } else {
        alert("added list is empty!")
      }
    },
    deleteTask(index) {
      if (index > -1) {
        this.appendedText.splice(index, 1);

      }
    }
  },
};
</script>

<template>
  <div class="bg-blue-400 h-screen p-10">
    <div class="w-1/2 mx-auto my-0 items-center justify-center bg-gray-500">
      <div class="bg-blue-500 text-center py-3 text-5xl ">To do list</div>
      <div class="bg-blue-500 text-3xl p-5 flex items-center justify-center"><input v-model="inputValue" type="text">
        <button @click="addTask()" class="text-gray-100 text-xs p-3 bg-green-800 rounded-lg ml-2">Add</button>
      </div>
    </div>
    <ul class="bg-blue-400 w-1/2 mx-auto my-0  ">
      <li v-for="(text, index) in appendedText" :key="index"
        class="bg-gray-100 my-4 px-2 flex justify-between items-center">
        {{ text }}<button @click="deleteTask(index)" class="text-2xl">X</button>
      </li>
    </ul>
  </div>
</template>


