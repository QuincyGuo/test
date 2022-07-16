<template>
  <div>
    <h1>canvas柱状图的绘制</h1>
    <!-- <canvas id="myCanvas"
            width="750"
            height="500"
            style="border:1px solid #d3d3d3;">
      您的浏览器不支持 HTML5 canvas 标签。
    </canvas> -->
    <svg class="box"
         viewBox='0 0 800 300'>
      <!-- 样式
      fill属性：设置填充颜色的 fill-opacity设置填充颜色的透明度 stroke：线的颜色
       -->
      <!-- 直线 -->
      <line x1="10"
            y1="20"
            x2="150"
            y2="20"
            stroke="red"
            stroke-width="2px"></line>
      <!-- 折线 -->
      <polyline points="10 50, 10 100, 120 50, 120, 100"
                fill-opacity="0"
                stroke="blue"></polyline>
      <!-- 矩形 -->
      <rect x="200"
            y="30"
            width="150"
            height="50"
            fill="pink"></rect>
      <!-- 圆 -->
      <circle cx='450'
              cy='60'
              r='50'
              style='stroke: cyan; fill:none'></circle>
      <!-- 椭圆 -->
      <ellipse cx="650"
               cy="60"
               rx="80"
               ry="30"
               style="fill: black; fill-opacity:0.5;"></ellipse>
      <!-- 多边形 -->
      <polygon points="30 150, 150 150, 70 200"
               stroke="red"
               fill-opacity="0" />
      <!-- 点与点之间连线，绘制任意图形 
               M 设置起点 L连线 Z 终点与起点闭合
               -->
      <path d="M 250 150
            L 300 200
            L 350 150
            L 400 200
            L 450 150
            L 350 120
            Z"></path>
    </svg>
  </div>
</template>

<script>
export default {
  name: 'AFather',

  data () {
    return {
      titleNameData: '456',
    }
  },
  mounted () {
    //this.doSomething();
  },
  methods: {
    doSomething () {
      let c = document.getElementById("myCanvas");
      let ctx = c.getContext("2d");
      // 设置为右上坐标系
      ctx.translate(50, 450);
      ctx.font = "20px 微软雅黑";
      ctx.fillText("FOOD", 50, 30);
      ctx.fillText("DIGITAL", 205, 30);
      ctx.fillText("LUGGAGE", 355, 30);
      ctx.fillText("FASHION", 515, 30);
      ctx.fillText("30", -40, -90);
      ctx.fillText("60", -40, -190);
      ctx.fillText("90", -40, -290);
      ctx.fillText("120", -50, -390);
      ctx.scale(1, -1);

      // 画坐标线
      ctx.fillStyle = "#131124";
      ctx.lineWidth = 2;
      ctx.moveTo(-10, 0);
      ctx.lineTo(640, 0);
      ctx.moveTo(0, -10);
      ctx.lineTo(0, 420);
      for (let i = 1; i < 4; i++) {
        ctx.moveTo(160 * i, 0);
        ctx.lineTo(160 * i, -10);
      }
      for (let i = 1; i < 5; i++) {
        ctx.moveTo(0, 100 * i);
        ctx.lineTo(-10, 100 * i);
      }
      ctx.stroke();

      ctx.fillStyle = "#ccccd6";
      ctx.lineWidth = 0.2;
      for (let i = 1; i < 5; i++) {
        ctx.moveTo(0, 100 * i);
        ctx.lineTo(800, 100 * i);
      }
      ctx.stroke();

      // 画矩形
      ctx.fillStyle = "#c02c38";
      ctx.fillRect(20, 1, 120, 190);
      ctx.fillRect(180, 1, 120, 300);
      ctx.fillRect(340, 1, 120, 200);
      ctx.fillRect(500, 1, 120, 400);

    }
  },


}
</script>

<style scoped>
.box {
  width: 800px;
  height: 300px;
  border: 1px solid rosybrown;
}
</style>
