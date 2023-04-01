<template>
  <div ref="myChart" style="height: 100%; width: 100%" />
</template>

<script setup>
import { onMounted, ref } from 'vue'
import * as echarts from 'echarts'

const myChart = ref()
const option = ref({
  "label": {
    "show": false,
    "position": "top"
  },
  "color": [
    "#57A7FE",
    "#EC955B",
    "#BADB9A",
    "#5DD7D1",
    "#FAA5C1",
    "#C73BE3",
    "#E56A0B",
    "#F7E73C",
    "#E9BAF9"
  ],
  "emphasis": {
    "focus": "series"
  },
  "itemStyle": {
    "normal": {
      "borderWidth": 5
    }
  },
  "legend": {
    "icon": "circle",
    "orient": "horizontal",
    "bottom": "bottom",
    "type": "scroll",
    "textStyle": {
      "fontSize": 12
    },
    "itemWidth": 10,
    "itemHeight": 10
  },
  "grid": {
    "top": 20,
    "right": 50,
    "left": 30,
    "bottom": "10%",
    "containLabel": true
  },
  "axisLabel": {
    "color": "#96B7DB",
    "fontWeight": 400,
    "fontSize": 14,
    "showMaxLabel": true,
    "showMinLabel": true
  },
  "xAxis": {
    "type": "category",
    "boundaryGap": true,
    "axisLabel": {
      "showMaxLabel": true,
      "showMinLabel": true,
      "color": "#96B7DB",
      "fontWeight": 400,
      "fontSize": 12,
      "overflow": "breakAll"
    },
    "axisTick": false,
    "axisLine": {
      "lineStyle": {
        "color": "#D9D9D9"
      }
    }
  },
  "yAxis": {
    "type": "value",
    "axisLabel": {
      "color": "#96B7DB",
      "fontWeight": 400,
      "fontSize": 12
    },
    "splitLine": {
      "lineStyle": {
        "type": "dashed"
      }
    },
    "scale": true
  },
  "tooltip": {
    "trigger": "axis",
    "confine": true,
    "axisPointer": {
      "lineStyle": {
        "color": "#96B7DB",
        "width": 2
      }
    },
    "extraCssText": "max-height:80%;overflow-y:auto",
    "enterable": true
  },
  "series": [
    {
      "type": "line",
      "seriesLayoutBy": "row",
      "smooth": true,
      "animation": true,
      "showSymbol": true,
      "symbol": "circle",
      "symbolSize": 5,
      "emphasis": {
        "focus": "series"
      },
      "lineStyle": {
        "shadowColor": "rgba(87,167,254,0.9)",
        "shadowBlur": 10,
        "shadowOffsetY": 5
      },
      "color": "rgba(87,167,254,1)",
      "stack": ""
    }
  ],
  "dataset": {
    "source": [
      [
        "分组",
        "2023-03-25(六)",
        "2023-03-26(日)",
        "2023-03-27(一)",
        "2023-03-28(二)",
        "2023-03-29(三)",
        "2023-03-30(四)",
        "2023-03-31(五)"
      ],
      [
        "APP启动.总次数",
        0,
        0,
        0,
        10,
        6,
        19,
        0
      ]
    ]
  },
})
onMounted(() => {
  const eCharts = echarts.init(myChart.value)
  eCharts.setOption(option.value, true)
})
</script>
<style scoped></style>
