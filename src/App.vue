<script setup>
import Table from './components/Table.vue'

</script>

<template>
  <FormClient v-if="isShowFrom" @close="close"></FormClient>



  <div class="container">
    <div class="tableNav">
      <h1>FrotEnd</h1>
      <button @click="showForm">New Client</button>
    </div>

  </div>
  <Table></Table>
</template>

<script>
import FormClient from './components/FormClient.vue'

export default {
  data() {
    return {
      isShowFrom: false
    }
  },
  components:{
    FormClient
  },
  methods:{
    close(){
      this.isShowFrom = false
    },
    showForm(){
      this.isShowFrom = true
    }
  }
};
</script>

<style scoped>
.container {
  width: 100%;
  display: flex;
  justify-content: center !important;
}

.tableNav {
  display: flex;
  width: 70%;
  justify-content: space-between;
  position: relative;
  margin-bottom: 30px;
}

h1,
button {
  display: flex;
  width: 25%;
}

</style>