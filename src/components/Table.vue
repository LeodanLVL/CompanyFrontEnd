<script setup>

import {ref} from 'vue'
  const url = "http://localhost:4000/api/"

  const clients = ref([]);

  const requestClient = async (url)=>{
    try {
    const req = await fetch(url+'clients/');
    const resp = await req.json();
    const {data} = resp;  
    // console.log(data);
    data.forEach(element => {
      console.log(element);
      clients.value.push(element);
    });
  
console.log(clients);
    } catch (error) {
  console.log(error);
}
  }
  requestClient(url);
</script>

<template>
    <div class="container">

        <table>
        <tr>
          <th>Name</th>
          <th>Email</th>
          <th>Phone</th>
          <th>Providers</th>
          <th>Edit</th>
        </tr>
        <tr v-for="client in clients" :key="client.id">
          <th>{{ client.name }}</th>
          <th>{{ client.email }}</th>
          <th>{{ client.phone }}</th>
          <th>
            <p v-for="provider in client.providers">{{ provider.name }}</p>
          </th>
          <th><button>edit</button></th>
        </tr>
      </table>
    </div>
</template>

<style scoped>
    table, th, td{
  border: solid 1px;
}
  table {
    border-collapse: collapse;
    width: 70%;
  }
  .container{
    width: 100%;
    display: flex;
    justify-content: center !important;
  }
</style>