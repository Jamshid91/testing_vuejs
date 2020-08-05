<template>
  <div class="workDay">
  <div class='header-workday'>
  <span>Начисления <br /> +6.000.000</span>
 <div class='line-text'>
  <span class='day-time'>Вы работали: <span class='day'>20 <sup>дня</sup></span> <span class='time'>160 <sup>часов</sup></span> <br /></span>
  <p>Рабочих дней в Июне месяце - <strong>22</strong> дня; Выходных -<strong>9</strong></p>
 </div>
  </div>
   <hr/>
    <ul>
      <TodoItem v-for="todo in todos" :todo="todo" :key="todo.id" />
    </ul>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";
export default {
  props: ["todos"],
  components: {
    TodoItem,
  },
};
</script>
<style scoped>
ul {
  margin: 0;
  padding: 0;
}
.workDay {
  display: block;
  background-color: #fff;
  margin: 0;
  padding: 10px 20px;
  border-radius: 5px;
}
.header-workday {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.day-time {
  display: flex;
  align-items: center;
    justify-content: space-between;
}
span {
   font-size: 22px;
   font-weight: 600;
   color: #2F4F4F;
}
.day,
.time {
  color: orange;
  font-size: 40px;
  font-weight: 700;
}
.time {
  color: grey;
}
sup {
  font-size: 20px;
  font-weight: 400;
}
p {
  color: grey;
  font-size: 18px;
}
strong {
  color: black;
}
</style>
