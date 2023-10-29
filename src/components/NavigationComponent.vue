<template>
  <nav id="navigaton" v-if="store.isLoggedIn">
    <ol>
      <li v-for="(link, index) in routes" :key="index">
        <router-link :to="link.path">{{ link.name }}</router-link>
      </li>
    </ol>
  </nav>
</template>

<script>
import { store } from '../../store';

export default {
  data() {
    return {
      routes: [
        {
          name: 'Home',
          path: '/home'
        },
        {
          name: 'About me',
          path: '/about-me'
        }
      ],
      store
    }
  },
}
</script>

<style>
#navigaton {
  padding: 1rem;
  background: #4609a3;
}

li {
  background: #8c5cda;
}

ol {
  list-style-type: none;
  padding: 0px;
}

a {
  display: block;
  padding: 10px;
  margin-bottom: 5px;
  font-weight: 800;
  text-decoration: none;
}
a:hover {
color: #cec000;
background-color: bisque;
}
</style>