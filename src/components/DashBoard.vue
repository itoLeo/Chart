<template>
  <div>
    <div class="upper">
      <div class="history">
        <div class="title">
          入場者数履歴
        </div>
        <div class="label_change">
          <div
          class="label_select"
          v-for="(label,index) in labels"
          :key="label.index"
          @click="historyClick(index)"
          v-bind:class="{'label_now' : index == historyLabel}"
          >
            {{label}}
          </div>
        </div>
        <component :is="currentType" />
        <VisitorsChart class="chart"/>
      </div>
    </div>
    <div class="rower">
      <div class="current">
        <div class="title">
          現在入退場者数
        </div>
      </div>
      <div class="stay">
        <div class="title">
          平均滞在時間
        </div>
        <div class="label_change">
          <div
          class="label_select"
          v-for="(label,index) in labels"
          :key="label.index"
          @click="stayClick(index)"
          v-bind:class="{'label_now' : index == stayLabel}"
          >
            {{label}}
          </div>
        </div>
        <StayTimeChart class="chart"/>
      </div>
    </div>
  </div>
</template>

<script>
import VisitorsChart from "./charts/VisitorsChart"
import StayTimeChart from "./charts/StayTimeChart"
export default {
  name: 'DashBoard',
  components: {
    VisitorsChart,
    StayTimeChart
  },
  data: function() {
      return {
          isClick: true,
          labels: ["日", "月", "年"],
          historyLabel: 0,
          stayLabel: 0,
      }
  },
  methods: {
    historyClick: function (index) {
      this.historyLabel = index
    },
    stayClick: function (index) {
      this.stayLabel = index
    }
  }
}
</script>

<style lang="scss">

.history {
  margin: 20px 0;
  height: 190px;
}
.chart {
  height: 150px;
  box-sizing: border-box;
  border: 4px solid #C4C4C4;
}
.current {
  margin-top: 10px;
  margin-right: 10%;
  width: 45%;
  height: 334px;

}
.stay {
  margin-top: 10px;
  width: 45%;
  height: 334px;
}
.title {
  border-bottom: 1px solid #000000;
  font-size: 16px;
}

.label_change {
  display: flex;
  height: 16px;
  margin-top: 4px;
  .label_select {
    width: 24px;
    text-align: center;
    background: #C4C4C4;
    font-size: 12px;
  }
  .label_now {
    width: 24px;
    text-align: center;
    background: #F2F2F2;
    font-size: 12px;
  }
}
.rower {
  display: flex;
}
</style>
