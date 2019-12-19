<template>
  <div class="wrapper">
    <Claim />
    <SearchInput />
  </div>
</template>

<script>
import axios from 'axios';

import debounce from 'lodash.debounce';
import Claim from '@/components/Claim.vue';
import SearchInput from '@/components/SearchInput.vue';

const API = 'https://images-api.nasa.gov/search';


export default {
  name: 'Search',
  components: { SearchInput, Claim },
  data() {
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
          this.results = response.data.collection.items;
        })
        .catch((error) => {
          console.log(error);
        });
    }, 500),
  },
};
</script>
<style lang="scss">
  .wrapper{
    display: flex;
    flex-direction: column;
    align-items: center;
    color: #fff;
    height: 100vh;
    margin: 0;
    padding: 30px;
    width: 100%;
    background-image: url("../assets/background.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: 40% 0;
  }
</style>
