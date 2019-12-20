<template>
    <input
      id="search"
      name="search"
      :class="{ dark: dark }"
      :value="value"
      @input="handleChange"
    />
</template>

<script>
export default {
  name: 'SearchInput',
  props: {
    value: {
      type: String,
      required: true,
    },
    dark: {
      type: Boolean,
      required: false,
    },
  },
  methods: {
    handleChange(e) {
      this.$emit('input', e.target.value);
    },
  },
};
</script>
<style lang="scss" scoped>
  input{
     text-align: center;
     color: #fff;
     font-size: 20px;
     font-weight: 400;
     height: 30px;
     border: none;
     border-bottom: 1px solid #fff;
     background: none;
     z-index: 10;
     transition: box-shadow .5s;

     @media (min-width: 1024px){
       font-weight: 600;
     }
   }
  input:focus{
    outline: none;
    box-shadow: 0 5px 13px -10px rgba(255,255,255, 0.4);
  }
  .dark{
    color: #1e3d4a;
    border-bottom-color: #1e3d4a;
  }
  .dark:focus {
    box-shadow: 0 5px 13px -10px rgba(#1e3d4a, 0.4);
  }


</style>
