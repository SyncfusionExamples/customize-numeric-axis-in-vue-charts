<template>
  <div id="app">
    <ejs-chart :primaryXAxis="chartPrimaryXAxis" :title="chartTitle" 
    :primaryYAxis="chartPrimaryYAxis">   
      <e-series-collection>
        <e-series type="Column" :dataSource="chartData" xName="overs" yName="englandScore"></e-series>
        <e-series type="Column" :dataSource="chartData" xName="overs" yName="westIndiesScore"></e-series>
      </e-series-collection>
    </ejs-chart>
  </div>
</template>

<script>
import Vue from "vue";
import { ChartPlugin, ColumnSeries } from '@syncfusion/ej2-vue-charts';
Vue.use(ChartPlugin);

export default {
  provide : { chart : [ColumnSeries] },
  data() {
    return {
      chartPrimaryYAxis : { title: 'Runs', rangePadding : 'Additional' },
      chartTitle : 'England vs West Indies',
      chartPrimaryXAxis : {
        valueType : 'Double',
        title : 'Death Overs',
        edgeLabelPlacement : 'Shift',
        minimum : 15,
        maximum : 21,
        interval : 1,
        labelFormat : '{value}th Over'
      },
      chartData : [
         { overs : 16, englandScore : 2, westIndiesScore : 7},
         { overs : 17, englandScore : 14,westIndiesScore : 7 },
         { overs : 18, englandScore : 7, westIndiesScore : 11 },
         { overs : 19, englandScore : 7, westIndiesScore : 8 },
         { overs : 20, englandScore : 10, westIndiesScore : 24 }
      ]
    };
  }
}
</script>

