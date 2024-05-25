<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="card" >
    <div class="container">
      <div>
        <div>Document</div>
        <div class="caption">Document tracking information</div>
      </div>
      <div>
        <div class="dropdown">
          <button class="dropbtn">
            Dropdown <i class="mdi mdi-chevron-down"></i>
          </button>
        </div>
      </div>
    </div>
    <table style="width: 100%; overflow-y: scroll;">
      <tr>
        <th
          v-for="(header, index) in headers"
          :key="index"
          :style="{ color: header.color }"
        >
          {{ header.name }}
        </th>
      </tr>
      <tr v-for="(row, index) in data" :key="index">
        <td>{{ row.name }}</td>
        <td>{{ row.file }}</td>
        <td>{{ row.category }}</td>
        <td>{{ row.author }}</td>
        <td :class="row.status === 'Send' ? 'success' : 'warning'">
          {{ row.status }}
        </td>
      </tr>
    </table>
  </div>
</template>
<script setup>
const headers = [
  {
    name: "Name",
    color: "black",
  },
  {
    name: "File",
    color: "black",
  },
  {
    name: "Category",
    color: "black",
  },
  {
    name: "Author",
    color: "black",
  },
  {
    name: "Status",
    color: "gray",
  },
];
const data = [
  {
    name: "Annual Report",
    file: "PDF",
    category: "Propert",
    author: "Diana Mathews",
    status: "Send",
  },
  {
    name: "Business plan",
    file: "WORD",
    category: "Crypto Currency",
    author: "Philip James",
    status: "Send",
  },
  {
    name: "Marketing Report",
    file: "PDF",
    category: "Content Creator",
    author: "Amanda Ross",
    status: "Pending",
  },
];
</script>
<style scoped>
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  border-radius: 5px;
  padding: 20px;
}
.container {
  display: flex;
  justify-content: space-between;
  padding: 8px;
}
.caption {
  color: gray;
  font-style: normal;
  font-size: 14px;
  padding: 10px 0px;
}
.dropbtn {
  background-color: #f0f1f3;
  /* color: white; */
  padding: 8px;
  font-size: 16px;
  border-radius: 5px;
  border: none;
  cursor: pointer;
}

table {
  border-collapse: collapse;
}

table,
th,
td {
  border: none;
  padding: 8px;
  /* margin: 16px; */
}

th {
  font-weight: bold;
  text-align: left;
}
.success {
  background-color: #d3e9da;
  border-radius: 5px;
  color: #80c19b;
  text-align: center;
}
.warning {
  background-color: #fcd8c5;
  color: #ecb19a;
  border-radius: 5px;
  text-align: center;
}
td {
    /* margin: 18px; */
}
</style>
