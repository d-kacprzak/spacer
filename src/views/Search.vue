<template>
  <div class="wrapper">
    <div class="search">
      <label for="search">Search</label>
      <input
        id="search"
        name="search"
        @input="handleInput"
        v-model="searchValue"
      />
      <ul>
        <li v-for="item in results" :key="item.data[0].nasa_id">
          <p>{{ item.data[0].description }}</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from 'axios';


import debounce from 'lodash.debounce';

const API = 'https://images-api.nasa.gov/search';


export default {
  name: 'Search',
  date() {
    return {
      searchValue: '',
      results: [],
    };
  },
  methods: {
    // eslint-disable-next-line func-names
    handleInput: debounce(function () {
      axios.get(`${API}?q=${this.searchValue}&media_type=image`)
        .then((response) => {
          console.log(response.data.collection.items);
        })
        .catch((error) => {
          console.log(error);
        });
    }, 500),
  },
};
</script>
