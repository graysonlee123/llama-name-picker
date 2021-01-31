<template>
  <button
    @click="$emit('clicked')"
    :data-text="text"
    :class="{ loading }"
  ></button>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      required: true,
    },
    loading: {
      type: Boolean,
      required: true,
    },
  },
}
</script>

<style scoped>
button {
  outline: none;
  height: 40px;
  text-align: center;
  width: 160px;
  border-radius: 40px;
  background-color: transparent;
  border-style: solid;
  letter-spacing: 1px;
  font-size: 12px;
  font-weight: bold;
  cursor: pointer;
  transition: all 0.25s ease;
  text-transform: uppercase;

  @apply text-indigo-500 border-indigo-500 border-2;
}

button:hover {
  @apply text-white bg-indigo-500;
}

button:active {
  letter-spacing: 2px;
}

button:focus {
  outline: none;
}

button::after {
  content: attr(data-text);
}

/* Loading */

button.loading {
  @apply border-gray-300 border-4 border-indigo-500;

  width: 40px;
  font-size: 0;
  border-right-color: white;
  border-bottom-color: white;
  border-left-color: white;
  animation: rotating 2s 0.25s linear infinite;
  cursor: not-allowed;
}

button.loading:hover {
  @apply bg-transparent text-indigo-500;
}

button.loading::after {
  content: '';
}

@keyframes rotating {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>
