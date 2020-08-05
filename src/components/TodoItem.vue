<template>
  <li>
    {{todo.title}}
    <hr />
    <span>{{todo.title2}}</span>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
span {
  color: rgb(17, 228, 228);
  font-weight: 600;
  margin-left: 400px;
}
li {
  list-style: none;
  padding-top: 15px;
  display: flex;
  align-items: center;
  font-size: 20px;
}
</style>
