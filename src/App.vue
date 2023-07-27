<script setup>
  import { ref, reactive } from 'vue';
  const lights = reactive([
    {id:1, lightImage:'//img.icons8.com/?size=512&id=12244&format=png', status:'On'},
    {id:2, lightImage:'//img.icons8.com/?size=512&id=12244&format=png', status:'On'},
    {id:3, lightImage:'//img.icons8.com/?size=512&id=75&format=png', status:'Off'}
  ])

  const handleClick = (id) => {
    const light = lights.find(light => light.id == id);
    light.status = light.status == 'On' ? 'Off' : 'On';
  }
</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Light Status with Vue 3</h1>
        <p class="p-5">Light will be On and Off</p>
        <div class="flex justify-between space-x-6">
            <div class="row">
              <div class="col-6 my-3">
                <div class="p-10 border w-96 flex flex-col space-y-5">
                    <button @click="handleClick(1)" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded my-4" :class="lights[0].status === 'On' ? 'bg-warning' : 'bg-secondary'">
                        Light 1 {{ lights[0].status }}
                    </button> <br>
                    <button @click="handleClick(2)" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded my-4" :class="lights[1].status === 'On' ? 'bg-warning' : 'bg-secondary'">
                        Light 2 {{ lights[1].status }}
                    </button> <br>
                    <button @click="handleClick(3)" class="bg-gray-500 hover:bg-gray-700 text-white font-bold py-2 px-4 rounded my-4" :class="lights[2].status === 'On' ? 'bg-warning' : 'bg-secondary'">
                        Light 3 {{ lights[2].status }}
                    </button>
                </div>
              </div>
              <div class="col-6">
                <div class="p-10 border w-96 flex flex-col space-y-5">
                    <img :src="lights[0].status === 'On' ? '//img.icons8.com/?size=512&id=12244&format=png' : '//img.icons8.com/?size=512&id=75&format=png'" style="width: 100px;"><br>
                    <img :src="lights[1].status === 'On' ? '//img.icons8.com/?size=512&id=12244&format=png' : '//img.icons8.com/?size=512&id=75&format=png'" style="width: 100px;"> <br>
                    <img :src="lights[2].status === 'On' ? '//img.icons8.com/?size=512&id=12244&format=png' : '//img.icons8.com/?size=512&id=75&format=png'" style="width: 100px;"> <br>
                </div>
              </div>
            </div>
        </div>
    </section>
</template>
