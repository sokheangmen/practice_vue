<template>
  <div class="container mt-5">
    <!-- Welcome section -->
    <button type="button" class="btn btn-danger" @click="createTask(task)">Create</button>
    <form>
      <div class="form-group">
        <label for="">firstName</label>
        <input type="text" class="form-control" id="firstname" v-model="firstname">
      </div>
      <div class="form-group">
        <label for="">lastName</label>
        <input type="text" class="form-control" id="lastname" v-model="lastname">
      </div>
      <div class="form-group">
        <label for="">Email</label>
        <input type="text" class="form-control" id="email" v-model="email">
      </div>
    </form>
    <h1 class="text-danger" v-if="users.length==0">No data</h1>
    <h1 class="text-success mt-5" v-else>List Name</h1>
    <table class="table mb-3">
      <thead>
        <tr>
          <th>ID</th>
          <th>Firstname</th>
          <th>Lastname</th>
          <th>Email</th>
        </tr>
      </thead>
      <tbody>
        <tr class="border-colab" v-for="user in users" :key="user.id">
          <td>{{user.id}}</td>
          <td>{{user.firstname}}</td>
          <td>{{user.lastname}}</td>
          <td>{{user.email}}</td>
          
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: [{
        id:1,
        firstname: 'heang',
        lastname: 'heang',
        email: 'heang@heang.com',
      }],
    };
  },
  computed:{
    task(){
      return {
        id:this.users.length +1,
        firstname: this.firstname,
        lastname: this.lastname,
        email: this.email,
      }
    }
  },
  methods :{
    createTask(task){
      this.users.push(task)
    }
  }
  
  
};
</script>

<style >

    .btn{
     width: 100px;
     margin: 10px;
     
    }
   
</style>