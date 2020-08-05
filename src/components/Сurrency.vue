<template>
  <div class="currency">
    <h4>Курс валют</h4>
    <span>
      <span class='usd'>USD</span>
      <div class="icon-tiny up">
        <i class="material-icons tiny ">call_made</i>
      </div>
      10210.00
      <div class="icon-tiny icon-received">
        <i class="material-icons tiny received">call_received</i>
      </div>
      10251.00
    </span>
    <span>
      EURO
      <div class="icon-tiny">
        <i class="material-icons tiny">call_made</i>
      </div>
      11000.00
      <div class="icon-tiny icon-received">
        <i class="material-icons tiny received">call_received</i>
      </div>
      11700.00
    </span>
  </div>
</template>

<style lang="scss" scoped>
.currency {
  display: inline-block;
  background-color: #fff;
  padding: 15px;
  border-radius: 5px;
  line-height: 5px ! important;
}
span {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 5px;
  color: #2F4F4F;
   font-weight: 700;
}
h4 {
  margin-top: 0 !important;
}
.icon-tiny {
  margin-left: 10px;
}
.usd {
  padding-right: 10px;
}
</style>
