<template>
  <div>
    <h1 class="p-2 flex bg-blue-200">User Profiles</h1>
    <div style="display: flex; flex-wrap: wrap;">
      <UserCard
        v-for="(user, index) in users"
        :key="index"
        :name="user.name"
        :age="user.age"
        :isActive="user.isActive"
        :hobby="user.hobby"
      />
    </div>
  </div>  
</template>

<script>
import UserCard from './components/userCard.vue';

export default {
  name: "App",
  components: {
    UserCard
  },
  data() {
    return {
      users: [
        { name: 'Leonard Lopez', age: 20, isActive: true, hobby: 'Watching Movie' },
        { name: 'Dwight Yana', age: 21, isActive: false, hobby: 'Skateboarding' },
        { name: 'Jarl Sabillano', age: 29, isActive: true, hobby: 'Basketball' },
        { name: 'Jay Macantan', age: 28, isActive: false, hobby: 'Eating' }
      ]
    };
  }
};
</script>