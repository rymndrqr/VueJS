<template>
    <div :class="cardClass" class="card">
      <h2>{{ name }}</h2>
      <p>Age: {{ age }}</p>
      <p>Hobby: {{ hobby }}</p>
      <StatusBadge :isActive="isActive" />
    </div>
  </template>
  
  <script>
  import StatusBadge from './StatusBadge.vue';
  
  export default {
    name: "UserCard",
    components: {
      StatusBadge
    },
    props: {
      name: {
        type: String,
        required: true
      },
      age: {
        type: Number,
        required: true
      },
      isActive: {
        type: Boolean,
        required: true
      },
      hobby: {
        type: String,
        required: true
      }
    },
    computed: {
      cardClass() {
        return {
          'young': this.age < 27,
          'active-border': this.isActive,
          'inactive-border': !this.isActive
        };
      }
    }
  };
  </script>
  
  <style scoped>
  .card {
    width: 220px;
    padding: 10px;
    margin: 10px;
    border: 2px solid;
    border-radius: 8px;
  }
  
  .young {
    background-color: whitesmoke;
  }
  
  .active-border {
    border-color: black;
  }
  
  .inactive-border {
    border-color: black;
  }
  </style>