<template>
    <span :class="badgeClass">
      {{ isActive ? 'Active' : 'Inactive' }}
    </span>
  </template>
  
  <script>
  export default {
    name: "StatusBadge",
    props: {
      isActive: {
        type: Boolean,
        required: true
      }
    },
    computed: {
      badgeClass() {
        return {
          'text-black-600': this.isActive,
          'text-black-600': !this.isActive
        };
      }
    }
  };
  </script>
  
  <style scoped>
  .text-black-600 {
    color: rgb(0, 0, 0);
  }
  .text-gray-500 {
    color: rgb(0, 0, 0);
  }
  </style>