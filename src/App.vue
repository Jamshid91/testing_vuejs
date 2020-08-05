<template>
  <div class="app">
    <div class="header">
      <h1>Поступления</h1>
      <div class="calendar">
        <i class="material-icons icon-c">date_range</i>
        <span>Май 02.2020-Июнь 02.2020</span>
      </div>
    </div>
    <div class="charts">
      <div class="accruals">
        <div class="text">
          <h4>Начисления</h4>
          <h3>6.000.000</h3>
          <div class="percent-text">
            <div class="icon-tiny">
              <i class="material-icons tiny">call_made</i>
            </div>
            0.22%
          </div>
        </div>
        <div class="question">
          <i class="fa fa-question-circle fa-2x"></i>
          <BarChart
            class="chart"
            :data-set="data1"
            :margin-left="0"
            :margin-top="0"
            :tick-count="0"
            :bar-padding="0.5"
          />
        </div>
      </div>
      <div class="withheld">
        <div class="text">
          <h4>Удержано</h4>
          <h3>5.000.000</h3>
          <div class="percent-text">
            <div class="icon-tiny">
              <i class="material-icons tiny">call_made</i>
            </div>
            5,16%
          </div>
        </div>
        <div class="question">
          <i class="fa fa-question-circle fa-2x"></i>
          <BarChart2
            class="chart2"
            :data-set="data2"
            :margin-left="0"
            :margin-top="0"
            :tick-count="0"
            :bar-padding="0.5"
          />
        </div>
      </div>
      <div class="yearFrom">
        <div class="text">
          <h4>Удержано</h4>
          <h3>14.000.000</h3>
          <div class="percent-text text-received">
            <div class="icon-tiny icon-received">
              <i class="material-icons tiny received">call_received</i>
            </div>
            0.74%
          </div>
        </div>
        <div class="question">
          <i class="fa fa-question-circle fasx fa-2x"></i>
          <BarChart2
            class="chart2"
            :data-set="data3"
            :margin-left="0"
            :margin-top="0"
            :tick-count="0"
            :bar-padding="0.5"
          />
        </div>
      </div>
          
          <div class="salary">
            <h4>Должностной оклад</h4>
            <h3>5.000.000   сум</h3>
            <canvas ref="canvas"></canvas>
          </div>
        </div>
    <div class="bases">
      <TodoList v-bind:todos="todos" />
      <div class="bases-right">
        <Currency />
        <Basic />
      </div>
    </div>
    
  </div>
</template>

<script>
import BarChart from "./components/BarChart.vue";
import BarChart2 from "./components/BartChart2.vue";
import TodoList from "@/components/TodoList";
import Currency from "./components/Сurrency";
import Basic from "./components/Basic";
import { Line} from 'vue-chartjs'

export default {
  name: "accruals",
   extends: Line,
  props: ['chartdata', 'options'],
  mounted() {
    this.renderChart(
      {
        labels: ['Январ', 'Февраль', 'Март', 'Апрель', 'Май', 'Июнь'],
        datasets: [{
            label: 'В этом месяц +37%',
            data: [8, 3, 10, 3, 5, 11],
            backgroundColor: [
                '#AFEEEE',
                // 'rgba(54, 162, 235, 0.2)',
                // 'rgba(255, 206, 86, 0.2)',
                // 'rgba(75, 192, 192, 0.2)',
                // 'rgba(153, 102, 255, 0.2)',
                // 'rgba(255, 159, 64, 0.2)'
            ],
            borderColor: [
              'blue'
                // 'rgba(255, 99, 132, 1)',
                // 'rgba(54, 162, 235, 1)',
                // 'rgba(255, 206, 86, 1)',
                // 'rgba(75, 192, 192, 1)',
                // 'rgba(153, 102, 255, 1)',
                // 'rgba(255, 159, 64, 1)'
            ],
            borderWidth: 1
        }]
      },
    );
  },
  data() {
    return {
      data1: [
        ["a", 23],
        ["b", 25],
        ["c", 29],
        ["d", 38],
        ["e", 34],
        ["f", 35],
      ],
      data2: [
        ["a2", 23],
        ["b2", 22],
        ["c2", 24],
        ["d2", 28],
        ["e2", 32],
        ["f2", 35],
      ],
      data3: [
        ["a3", 23],
        ["b3", 22],
        ["c3", 24],
        ["d3", 28],
        ["e3", 32],
        ["f3", 30],
      ],

      todos: [
        {
          id: 1,
          title: "Оклад по штатному расписанию",
          title2: "+2.000.000",
          completed: false,
        },
        {
          id: 2,
          title: "Персональная надбавка",
          title2: "+350.000",
          completed: false,
        },
        {
          id: 3,
          title: "Надбавка по выслогулет сотдудника",
          title2: "+200.000",
          completed: false,
        },
        {
          id: 4,
          title: "Ежемесячная премия",
          title2: "+800.000",
          completed: false,
        },
        {
          id: 5,
          title: "Квартальная премия",
          title2: "+2.000.000",
          completed: false,
        },
        {
          id: 6,
          title: "Социальная защита (Питания)",
          title2: "+150.000",
          completed: false,
        },
      ],
    };
  },
  components: {
    BarChart,
    BarChart2,
    TodoList,
    Currency,
    Basic,
  },
};
</script>

<style>
h1,
h2,
h3,
h4,
h5,
p,
span,
sup, strong {
   font-family: 'Montserrat', sans-serif;
}

.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 30px;
}

.calendar {
  background-color: #fff;
  display: flex;
  align-items: center;
  padding: 5px 20px;
  border-radius: 5px;
  cursor: pointer;
}
.calendar:hover {
  box-shadow: 5px 5px 10px grey;
}
.icon-c {
  margin-right: 20px;
  color: rgb(248, 144, 162);
}
.charts {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.fasx {
  margin-right: 10px;
}
.icon-tiny {
  width: 30px;
  height: 30px;
  background-color: rgb(25, 238, 25);
  border-radius: 50%;
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 20px;
}
.icon-received {
  background-color: pink;
}
.text-received {
  color: rgb(248, 144, 162) !important;
}
.text {
  direction:flex;
  justify-content: space-between;
  flex-direction: column;
  height: 200px;
}
.percent-text {
  display: flex;
  align-items: center;
  color: rgb(25, 238, 25);
}
.question {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 200px;
}
.fa-question-circle {
  color: #ccc6;
  text-align: right;
}
.accruals,
.withheld,
.yearFrom {
  display: flex;
  align-items: center;
  justify-self: space-between;
  background-color: #fff;
  border-radius: 5px;
  width: 250px;
  padding: 10px;
}
.accruals:hover,
.withheld:hover,
.yearFrom:hover,
.salary:hover {
  cursor: pointer;
  box-shadow: 5px 5px 10px grey;
}
.chart2 {
  color: red;
}
.bases {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 40px;
}
.bases-right {
  display: flex;
  flex-direction: column;
}
.basic {
  margin-top: 20px;
}
.salary {
  width: 250px;
  background-color: #fff;
  line-height: 5px;
  padding:5px;
  border-radius: 5px;
}
canvas {
  width: 250px;
}
</style>
