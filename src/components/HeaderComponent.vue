<template>
  <div class="header">
    <div class="logo">
      <img src="../assets/logo.svg" />
    </div>
    <div class="user">
      <div v-if="store.isLoggedIn" >
        <div class="avatar" :style="{ backgroundColor: getRandomColor() }"></div>
        <div class="user-details">{{ fullName }}</div>
      </div>
      <div class="separator"></div>
      <button class="pill-button" @click="store.loginManager()">{{ store.isLoggedIn ? 'LOGOUT' : 'LOGIN' }}</button>

    </div>
  </div>
</template>

<script>
import { store } from '../../store';

export default {
  
  data() {
    return {
      store
    }
  },
  computed: {
    fullName() {
      return `${store.user.name} ${store.user.surname}`;
    }
  },
  methods: {
        getRandomColor() {
      const letters = "0123456789ABCDEF";
      let color = "#";
      for (let i = 0; i < 6; i++) {
        color += letters[Math.floor(Math.random() * 16)];
      }
      return color;
    },
}
}
</script>

<style>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  background-color: #741afc;
}

.logo {
  display: flex;
  align-items: flex-end;
  
}
h3 {
padding-left: 150  px;
  
}
.user-details {
  text-align: right;
  color: white;
  margin-right: 10px;
}
.separator {
  width: 1px; 
  height: 40px; 
  background-color: white;
  margin: 0 10px; 
}

.user {
  
  display: flex;
  align-items: center;
}

.avatar {
  width: 40px; 
  height: 40px; 
  text-align: center;
  align-items: center !important;
  background-color: #2c1272; 
  border-radius: 50%; 
}

h3 {
  font-weight: 800;
  
}

button {
    background: none;
    border: none;
    color: White; 
    font-size: 16px;
    cursor: pointer;
  }
  .pill-button {
  background-color: #7a2270; 
  color: #34164d; 
  border: none;
  border-radius: 20px; 
  padding: 5px 15px; 
  font-size: 16px;
  cursor: pointer;
  outline: none;
}
.pill-button:hover {
  background-color: #7a2270; 
}
  
</style>