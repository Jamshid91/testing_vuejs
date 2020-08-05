<template>
  <div class="basic">
    <div class="basic-c">
      <div class="basic-sum">
        <h3>679.330</h3>
      </div>
      <p>
        Базовая расчётная <br />
        величина (сум)
      </p>
    </div>
    <div class="basic-c">
      <div class="basic-sum">
        <h3>223.000</h3>
      </div>
      <p>
        Минимальный <br />
        размер заработной <br />
        платы(сум)
      </p>
    </div>
    <div class="basic-c">
      <div class="basic-sum">
        <h3 class='end'>12.5%</h3>
      </div>
      <p>
        Подоходный <br />
        налог %
      </p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.basic {
  display: inline-block;
  background-color: #fff;
  border-radius: 5px;
  padding: 15px;
}
.basic-c {
  display: flex;
  align-items: center;
}
.basic-sum {
  background-color: #ccc7;
  border-radius: 5px;
  padding: 10px 15px;
  margin-right: 25px;
}
h3 {
  margin: 0 !important;
}
.end {
  padding: 0 15px;
}
p {
  font-size: 14px;
}
</style>
