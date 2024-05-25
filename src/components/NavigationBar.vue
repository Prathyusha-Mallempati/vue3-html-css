<template>
  <div class="sidebar">
    <div class="title">CRM.io</div>
    <div class="dashboard">
      <i class="mdi mdi-view-dashboard" style="padding-right: 5px"></i>
      <span>Dashboard</span>
    </div>
    <div class="title-padding">Management</div>
    <ul class="border">
      <li v-for="(item, index) in management" :key="index">
        <a href="#">
          <i :class="item.icon" style="padding-right: 5px"></i
          >{{ item.name }}</a
        >
      </li>
    </ul>
    <div>Connection</div>
    <ul class="border">
      <li v-for="(item, index) in connections" :key="index">
        <a href="#">
          <i :class="item.icon" style="padding-right: 5px"></i
          >{{ item.name }}</a
        >
      </li>
    </ul>
    <div>Customer</div>
    <ul>
      <li v-for="(item, index) in customers" :key="index">
        <a href="#">
          <i :class="item.icon" style="padding-right: 5px"></i
          >{{ item.name }}</a
        >
      </li>
    </ul>
  </div>
</template>
<script setup>
import "@mdi/font/css/materialdesignicons.min.css";
const management = [
  {
    name: "Document",
    icon: "mdi mdi-file-document",
  },
  {
    name: "Contact",
    icon: "mdi mdi-contacts",
  },
  {
    name: "Prospect",
    icon: "mdi mdi-content-paste",
  },
  {
    name: "Work flow",
    icon: "mdi mdi-sync",
  },
];
const connections = [
  {
    name: "Chat Integration",
    icon: "mdi mdi-wechat",
  },
  {
    name: "Marketing Automation",
    icon: "mdi mdi-home-automation",
  },
  {
    name: "Email Integration",
    icon: "mdi mdi-email",
  },
];

const customers = [
  {
    name: "Transaction",
    icon: "mdi mdi-transcribe",
  },
  {
    name: "Maintenance",
    icon: "mdi mdi-inbox",
  },
];
</script>
<style scoped>
.bg-img {
  position: fixed;
  bottom: 0px;
  width: 230px;
}
.title {
  color: orange;
  padding: 20px 0px;
  font-weight: bold;
  font-style: italic;
}
.dashboard {
  background-color: #3a63ad;
  color: white;
  border-radius: 5px;
  padding: 10px;
}
.title-padding {
  padding: 20px 10px 0px;
}
body {
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
}

.sidebar {
  width: 230px;
  background-color: rgb(3, 3, 59);
  height: 100%;
  /* position: fixed; */
  left: 0;
  top: 0;
  padding: 10px;
  @media screen and (max-width: 1025px) {
    width: 170px !important;
  }
  @media screen and (max-width: 769px) {
    width: 120px !important;
  }
  @media screen and (max-width: 575px) {
    width: 230px !important;
  }
}

ul {
  list-style-type: none;
  padding: 0;
}

.border {
  border-bottom: 1px solid #555;
}

a {
  display: block;
  padding: 15px;
  color: white;
  text-decoration: none;
}

a:hover {
  background-color: #555;
}
</style>
