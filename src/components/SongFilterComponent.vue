<template>
  <div class="songFilter">
    <button class="pill-button" @click="applyFilter('None')" :class="{ active: activeFilter === 'None' }">None</button>
    <button class="pill-button" @click="applyFilter('Name')" :class="{ active: activeFilter === 'Name' }">Name</button>
    <button class="pill-button" @click="applyFilter('Artist')" :class="{ active: activeFilter === 'Artist' }">Artist</button>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'SongFilterComponent',
  props: {
    onFilterChanged: Function,
  },
  setup(props) {
    
    const activeFilter = ref('None');

    const applyFilter = (filter) => {
      activeFilter.value = filter;
      props.onFilterChanged(filter);
    };

    return {
      activeFilter,
      applyFilter,
    };
  },
};
</script>

<style scoped>
.songFilter {
  text-align: center;
  padding: 20px;
}

button {
  margin: 5px;
  padding: 5px 10px;
  background-color: #3498db;
  color: #fff;
  border: none;
  cursor: pointer;
  outline: none;
}

.pill-button:active {
  background-color: #000000;
  color: #000;
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
  background-color: #c75dbb; 
}
</style>