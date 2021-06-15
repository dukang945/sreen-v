<template>
  <div>
    <header id="header">
      <h3 class="header-title">大屏数据可视化-地质大学</h3>
    </header>

    <div id="container">
      <div id="flexCon">
        <div class="flex-row">
          <div class="flex-cell flex-cell-l">
            <div class="chart-wrapper">
              <h3 class="chart-title">图表</h3>
              <div class="chart-div">
                <!-- <div class="chart-loader"><div class="loader"></div></div> -->
                <div
                  id="myChart1"
                  :style="{ width: '100%', height: '100%' }"
                ></div>
              </div>
            </div>
          </div>
          <div class="flex-cell flex-cell-c">
            <div class="chart-wrapper">
              <h3 class="chart-title">图表</h3>
              <div class="chart-div"></div>
              <div class="chart-loader"><div class="loader"></div></div>
            </div>
          </div>
          <div class="flex-cell flex-cell-r">
            <div class="chart-wrapper">
              <h3 class="chart-title">图表</h3>
              <div class="chart-div">
                <div class="chart-loader"><div class="loader"></div></div>
              </div>
            </div>
          </div>
        </div>
        <div class="flex-row">
          <div class="flex-cell flex-cell-lc">
            <div class="chart-wrapper">
              <h3 class="chart-title">图表</h3>
              <div class="chart-div chart-done">
                <div class="chart-loader"><div class="loader"></div></div>
              </div>
            </div>
          </div>
          <div class="flex-cell flex-cell-r">
            <div class="chart-wrapper">
              <h3 class="chart-title">图表</h3>
              <div class="chart-div chart-done">
                <div class="chart-loader"><div class="loader"></div></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  mounted () {
    this.drawLine()
  },
  methods: {
    drawLine () {
      let myChart1 = this.$echarts.init(document.getElementById('myChart1'))
      const options = {
        color: [
          '#4992ff',
          '#7cffb2',
          '#fddd60',
          '#ff6e76',
          '#58d9f9',
          '#05c091'
        ],
        textStyle: {
          color: '#B9B8CE'
        },
        timeAxis: {
          axisLine: { color: '#B9B8CE' },
          splitLine: { color: '#484753' }
        },
        title: {
          text: null
        },
        tooltip: {
          trigger: 'axis',
          axisPointer: {
            type: 'cross',
            label: {
              backgroundColor: '#6a7985'
            }
          }
        },
        legend: {
          data: ['邮件营销', '联盟广告', '视频广告', '直接访问', '搜索引擎']
        },
        grid: {
          left: '3%',
          right: '4%',
          bottom: '3%',
          containLabel: true
        },
        xAxis: [
          {
            type: 'category',
            boundaryGap: false,
            data: ['周一', '周二', '周三', '周四', '周五', '周六', '周日']
          }
        ],
        yAxis: [
          {
            type: 'value'
          }
        ],
        series: [
          {
            name: '邮件营销',
            type: 'line',
            stack: '总量',
            areaStyle: {},
            emphasis: {
              focus: 'series'
            },
            data: [120, 132, 101, 134, 90, 230, 210]
          },
          {
            name: '联盟广告',
            type: 'line',
            stack: '总量',
            areaStyle: {},
            emphasis: {
              focus: 'series'
            },
            data: [220, 182, 191, 234, 290, 330, 310]
          },
          {
            name: '视频广告',
            type: 'line',
            stack: '总量',
            areaStyle: {},
            emphasis: {
              focus: 'series'
            },
            data: [150, 232, 201, 154, 190, 330, 410]
          },
          {
            name: '直接访问',
            type: 'line',
            stack: '总量',
            areaStyle: {},
            emphasis: {
              focus: 'series'
            },
            data: [320, 332, 301, 334, 390, 330, 320]
          },
          {
            name: '搜索引擎',
            type: 'line',
            stack: '总量',
            label: {
              show: true,
              position: 'top'
            },
            areaStyle: {},
            emphasis: {
              focus: 'series'
            },
            data: [820, 932, 901, 934, 1290, 1330, 1320]
          }
        ]
      }
      myChart1.setOption(options)
    }
  }
}
</script>

<style>
body {
  position: relative;
  font-family: 'Microsoft Yahei', Arial, sans-serif;
  background: rgb(40, 30, 47) url('../assets/img/bg.png') 0 0 / 100% 100%
    no-repeat;
}

/* layout */
#header {
  position: relative;
  height: 72px;
  background: url('../assets/img/header.png') 0 0 / 100% 100% no-repeat;
  overflow: hidden;
}
.header-title {
  line-height: 64px;
  text-align: center;
  font-size: 32px;
  font-weight: 400;
  color: #bef2ff;
}
#container {
  position: absolute;
  top: 64px;
  bottom: 15px;
  left: 0;
  right: 0;
}

#flexCon {
  height: 100%;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  -webkit-flex-direction: column;
  -ms-flex-direction: column;
  flex-direction: column;
}
.flex-row {
  -webkit-flex: 1;
  -ms-flex: 1;
  flex: 1;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
}
.flex-cell {
  -webkit-flex: 1;
  -ms-flex: 1;
  flex: 1;
  padding: 15px;
}
.flex-cell-l,
.flex-cell-r {
  -webkit-flex: 2;
  -ms-flex: 2;
  flex: 2;
}
.flex-cell-c {
  -webkit-flex: 3;
  -ms-flex: 3;
  flex: 3;
}
.flex-cell-lc {
  -webkit-flex: 5;
  -ms-flex: 5;
  flex: 5;
}

.chart-wrapper {
  position: relative;
  height: 100%;
}
.chart-title {
  height: 30px;
  font-size: 20px;
  font-weight: normal;
  color: #5ac8fa;
}
.chart-div {
  position: absolute;
  top: 30px;
  bottom: 0;
  left: 0;
  right: 0;
  border-style: solid;
  border-width: 26px 27px 27px;
  border-image: url('../assets/img/chart-wrapper.png') 26 27 27 fill / 1 / 0
    repeat;
}

/* media query */
@media (max-width: 1900px) {
  #header {
    height: 48px;
  }
  #container {
    top: 36px;
    bottom: 10px;
  }
  .header-title {
    line-height: 42px;
    font-size: 22px;
  }
  .flex-cell {
    padding: 10px;
  }
  .chart-title {
    height: 24px;
    font-size: 16px;
  }
  .chart-div {
    top: 24px;
  }
}

/* chart-loader */
.chart-loader {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 99;
  width: 100%;
  height: 100%;
  background: rgba(255, 255, 255, 0);
  transition: all 0.8s;
}
.chart-loader .loader {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 60px;
  height: 60px;
  margin: -30px 0 0 -30px;
  border: 3px solid transparent;
  border-top-color: #3498db;
  border-radius: 50% !important;
  -webkit-animation: spin 2s linear infinite;
  animation: spin 2s linear infinite;
}
.chart-loader .loader:before {
  content: '';
  position: absolute;
  top: 3px;
  left: 5px;
  right: 5px;
  bottom: 5px;
  border: 3px solid transparent;
  border-top-color: #e74c3c;
  border-radius: 50% !important;
  -webkit-animation: spin 3s linear infinite;
  animation: spin 3s linear infinite;
}
.chart-loader .loader:after {
  content: '';
  position: absolute;
  top: 9px;
  left: 10px;
  right: 10px;
  bottom: 10px;
  border: 3px solid transparent;
  border-top-color: #f9c922;
  border-radius: 50% !important;
  -webkit-animation: spin 1.5s linear infinite;
  animation: spin 1.5s linear infinite;
}
.chart-done .chart-loader {
  display: none;
}
@-webkit-keyframes spin {
  0% {
    -webkit-transform: rotate(0deg);
    -ms-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(360deg);
    -ms-transform: rotate(360deg);
    transform: rotate(360deg);
  }
}
@keyframes spin {
  0% {
    -webkit-transform: rotate(0deg);
    -ms-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(360deg);
    -ms-transform: rotate(360deg);
    transform: rotate(360deg);
  }
}
</style>
