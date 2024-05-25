<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="card">
    <div class="title">Popular Product</div>
    <div v-for="(item, index) in products" :key="index">
      <div class="container">
        <div class="circle"></div>
        <div>
          <div class="title">
            {{ item.title }}
          </div>
          <div class="caption">
            {{ item.price }}
          </div>
        </div>
      </div>
    </div>
    <div class="title chat">Chat</div>
    <div v-for="(item, index) in chats" :key="index" class="name">
      <div class="container">
        <div class="circle"></div>
        <div>
          <div class="title">
            {{ item.title }}
          </div>
          <div class="caption">
            {{ item.price }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
const products = [
  {
    title: "Gadget Converter",
    price: "$ 250",
  },
  {
    title: "Lens Camera",
    price: "$ 50",
  },
  {
    title: "Airpods",
    price: "$ 100",
  },
  {
    title: "MacBook",
    price: "$ 999",
  },
];

const chats = [
  {
    title: "Prathyusha",
    price: "How is my product ?",
  },
  {
    title: "Greeshma",
    price: "How is my product ?",
  },
  {
    title: "Gagana",
    price: "How is my product ?",
  },
  {
    title: "Venky",
    price: "How is my product ?",
  },
];
</script>
<style scoped>
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  border-radius: 5px;
  padding: 20px;
  margin: 0px 20px 
}
.container {
  display: flex;
  justify-content: left;
  gap: 20px;
  padding: 10px 0px;
}
.circle {
  width: 30px;
  height: 30px;
  background-color: #081A3B; 
  border-radius: 50%; 
  margin-right: 10px;
}
.title {
  font-weight: bold;
}
.caption {
  color: gray;
  font-size: 12px;
}
.chat {
    margin-top: 30px;
}
</style>
