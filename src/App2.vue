<script>
export default {
  data(){
    return {
      name: 'John Doe',
      status : 'pending',
      tasks:['Tasks One', 'Task Two', 'Task Three'],
      link: 'https://google.com',
    };
  },
  methods:{
    toggleStatus(){
      if(this.status === 'active'){
        this.status='pending';
      }
      else if(this.status==='pending'){
        this.status='inactive';

      }
      else{
        this.status='active';
      }
    }
  }
}

</script>


<template>
<h1>{{ name }}</h1>
<p v-if="status === 'active' ">User is Active</p>
<p v-else-if="status === 'pending' ">User is Pending</p>

<p v-else>User is Inactive</p>
<h3>Tasks:</h3>
<ul>
  <li v-for="task in tasks" :key="'task'">{{ task }}</li>
</ul>
<a v-bind:href="link">Google</a>
<br/>
<!-- <button v-on:click="toggleStatus">Change Status</button> -->
<button @click="toggleStatus">Change Status</button>

</template>/


<style scoped>

</style>

<!-- <script setup>
import {ref , onMounted} from "vue";

    const name = ref('John Doe');
    const status=ref('active');
    const tasks = ref(['Tasks One', 'Tasks Two', 'Taks Three'])
    const newTask = ref('')
    const toggleStatus=()=>{
      if(status.value === 'active'){
        status.value='pending';
      }
      else if(status.value==='pending'){
        status.value='inactive';

      }
      else{
        status.value='active';
      }

    }

    const addTask=()=>{
      if(newTask.value.trim() !== ''){ 
        tasks.value.push(newTask.value);
        newTask.value = '';
      }

    };
    const deleteTask=()=>{
      tasks.value.splice(index,1);

    }

    onMounted( async()=>{
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/todos')
        const data = await response.json();
        tasks.value = data.map((task) => task.title);
      }
      catch(error){
        console.log("Error Fetchng Tasks")
      }
    });

</script>


<template>
<h1>{{ name }}</h1>
<p v-if="status === 'active' ">User is Active</p>
<p v-else-if="status === 'pending' ">User is Pending</p>

<p v-else>User is Inactive</p>

<form @submit.prevent="addTask">
  <label for="newTask">Add Task</label>
  <input type="next" id="newTask" name="newTask" v-model="newTask" />
  <button type="submit">ADD </button>
</form>
<h3>Tasks:</h3>
<ul>
  <li v-for="{task , index} in tasks" :key="'task'">
    <span>
      {{ task }}

    </span>
    <button @click="deleteTask(index)">X</button>

  </li>
</ul>
<button @click="toggleStatus">Change Status</button>

</template>/


<style scoped>

</style> -->

