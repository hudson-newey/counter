<script setup lang="ts">
import { Menu, CircleX } from "lucide-vue-next";
import { ref } from "vue";

const iconSize = 30;

const open = ref(false);
const listItems = ref<string[]>([]);
</script>

<template>
  <div>
    <template v-if="!open">
      <Menu @click="open = true" :size="iconSize" class="p-3" />
    </template>

    <template v-else>
      <div>
        <CircleX @click="open = false" :size="iconSize" class="p-3" />

        <ul>
          <li v-for="(item, index) in listItems" :key="index">{{ item }}</li>
        </ul>

        <!-- TODO: replace with a form -->
        <div>
          <button type="submit" class="button">Add Counter</button>
        </div>
      </div>
    </template>
  </div>
</template>
