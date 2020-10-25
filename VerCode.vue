<template>
  <div class="">

    <canvas ref="c1"
            id="c"
            width="100px"
            height="50px"></canvas>

  </div>
</template>

<script>
export default {
  components: {

  },
  props: {
    count: Number
  },
  data () {
    return {

    };
  },
  computed: {

  },
  created () {

  },
  mounted () {
    this.getCan()
  },
  methods: {
    getCan () {
      //获取随机数
      let countArr = [];

      console.log(countArr);
      console.log("初始化画布");
      var canvas = document.querySelector("canvas")
      var ctx = canvas.getContext('2d');
      // 绘制矩形边框

      ctx.strokeRect(0, 0, 100, 50)
      ctx.fillStyle = "rgba(0,143,214,.6)";
      ctx.fillRect(0, 0, 100, 50);

      var num1 = Math.floor(Math.random() * 10)
      var num2 = Math.floor(Math.random() * 10)
      var num3 = Math.floor(Math.random() * 10)
      var num4 = Math.floor(Math.random() * 10)
      let all = num1.toString()+num2.toString()+num3.toString()+num4.toString()
      console.log(all);
      this.$emit("vercode",all)
      ctx.beginPath();
      ctx.font = " 20px  '宋体' "
      ctx.strokeStyle = 'rgb(245,245,0,.6)';
      // 描边文字
      ctx.strokeText(num1, 15, 22);
      ctx.strokeText(num2, 35, 30);
      ctx.strokeText(num3, 55, 20);
      ctx.strokeText(num4, 75, 40);

      //  ctx.fillStyle = "hsla(125,80%,60%,1)";
      // ctx.strokeStyle = "hsla(125,80%,60%,1)";
      ctx.closePath();


    }
  },
};
</script>

<style scoped lang="scss">
#c {
}
</style>
