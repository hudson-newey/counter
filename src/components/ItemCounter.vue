<script setup lang="ts">
import { Plus, Minus } from "lucide-vue-next";
import { ref } from "vue";

const count = ref(0);

function handleKeyDown(event: KeyboardEvent) {
  switch (event.key) {
    case "+": {
      count.value++;
      break;
    }

    case "-": {
      count.value--;
      break;
    }

    case "_": {
      count.value--;
      break;
    }

    case "=": {
      count.value++;
      break;
    }
  }
}

document.addEventListener("keydown", handleKeyDown);
</script>

<template>
  <div class="has-text-centered">
    <h1 class="title is-size-1">
      <output>{{ count }}</output>
    </h1>

    <div class="is-flex is-justify-content-center is-gap-1">
      <button @click="count++" class="button is-large is-primary">
        <Plus :size="38" />
      </button>

      <button @click="count--" class="button is-large is-dark">
        <Minus :size="38" />
      </button>
    </div>
  </div>
</template>
