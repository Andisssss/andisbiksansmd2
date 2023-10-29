<template>
  <div class="aboutMe">
    <h1>ABOUT ME</h1>
    <button @click="toggleFormEditing">{{ editFormButtonLabel }}</button>
    <FormComponent :disabled="isFormDisabled" />
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'AboutMeComponent',
  setup() {
    const isFormEditing = ref(false);

    const toggleFormEditing = () => {
      isFormEditing.value = !isFormEditing.value;
    };

    return {
      isFormEditing,
      toggleFormEditing,
    };
  },
  computed: {
    editFormButtonLabel() {
      return this.isFormEditing ? 'CANCEL' : 'EDIT FORM';
    },
    isFormDisabled() {
      return !this.isFormEditing;
    },
  },
};
</script>

<style scoped>
.aboutMe {
  text-align: center;
  padding: 20px;
  height: 882px;
  background-color: #310574;
}

button {
  background-color: #064444;
  color: #fff;
  border: none;
  padding: 15px 10px;
  cursor: pointer;
  outline-width: 2px;
}

h1,h3{
  color:white;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif ; 
}
</style>