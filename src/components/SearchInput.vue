<template>
  <div class="searchWrapper">
    <input
      id="search"
      name="search"
      @input="handleInput"
      v-model="searchValue"
    />
  </div>
</template>

<script>
export default {
  name: 'SearchInput',
};
</script>
<style lang="scss" scoped>
  .searchWrapper{
    margin-top: 50px;
    display: flex;
    flex-direction: column;
    width: 250px;

    input{
      height: 30px;
      border: none;
      border-bottom: 1px solid black;
      background: none;
    }
  }
</style>
