<template>
  <div class="cicle12" @mouseenter="show" @mouseleave="hide">
    <span>{{ title }}</span>
    <p class="p1">{{ score }}</p>
    <p class="p2">{{ level }}</p>
<!--    <pi v-show="visible">-->
<!--      {{ description }}-->
<!--    </pi>-->
<!--    <tree class="tree" id="tree12" v-show="visible">-->
<!--    <li><span class="caret">与用户有过协作的用户数量</span>-->
<!--      <ul class="nested">-->
<!--        <li>总分</li>-->
<!--        <li>100</li>-->
<!--      </ul>-->
<!--    </li>-->
<!--    <li><span class="caret">用户与协作者之间的紧密程度</span>-->
<!--      <ul class="nested">-->
<!--        <li>总分</li>-->
<!--        <li>90</li>-->
<!--      </ul>-->
<!--    </li>-->
<!--  </tree>-->

  </div>
</template>

<script setup>
import { ref,toRefs,defineProps } from "vue";
// 使用props接收父组件传递的数据
const props = defineProps({
  title: String, // 圆形组件的标题
  score: Number, // 圆形组件的总分
  level: String, // 圆形组件的等级
  description: String, // 圆形组件的描述
});

// 解构props对象
const {title, score, level, description } = toRefs(props);

    const visible = ref(false); // 定义一个响应式变量，控制弹出框和文本框的显示
    const show = () => {
      visible.value = true; // 鼠标移入时，设置为true
    };
    const hide = () => {
      visible.value = false; // 鼠标移出时，设置为false
    };

</script>

<style lang="less">
.cicle12{
  width: 3.2rem;
  height: 3.2rem;
  position: absolute;
  top: 70%;
  left: 50%;
  z-index: 100;
  margin-left: -1.5rem;
  border-radius: 50%;
  transition: transform 0.5s;
  background     : url("~@/images/circle2.png") no-repeat;
  background-size: 100%;
  color:#93c6de;
  animation      : rotate9 50s linear infinite;
  span {
    position: relative;
    /* 设置元素相对于其正常位置的偏移量 */
    top: 0px; /* 向下偏移 10 像素 */
    left: 10px; /* 向右偏移 20 像素 */
    font-family: 'LCdd';
    display: block;
    margin-left: 25%;
    font-size: 0.3rem;
    margin-top: 20%;
  }
  .p1 {
    position: relative;
    top: -10px; /* 向下偏移 10 像素 */
    left: 0px; /* 向右偏移 20 像素 */
    text-align: center;
    font-size: 1rem;
    font-family: 'LCdd';
    color:#f39c12;
  }
  .p2{
    position: relative;
    top: -20px; /* 向下偏移 10 像素 */
    left: 0px; /* 向右偏移 20 像素 */
    text-align: center;
    font-size: 0.5rem;
    font-family: 华文中宋;
    color: #93c6de;
  }
  ul
  {
    li{
      float: left;
      color: #ec1717;
      font-size: 0.2rem;
      margin-left: 5%;
      span{
        float: left;
        color: #fff;
        font-size: 0.3rem;
        margin-left: 5%;
      }
    }
  }
  & :hover{
    //transform: scale(1.2);
  }

}

@keyframes rotate9 {
  0% {
    transform: matrix3d(0.65, 0, 0, 0, 0, 0.65, 0, 0, 0, 0, 1, 0, -134.3242, -60, 0, 1);
    z-index  : 99.01771;
  }

  1% {
    transform: matrix3d(0.57714, 0, 0, 0, 0, 0.57714, 0, 0, 0, 0, 1, 0,-133.4242, -61.3424, 0, 1);
    z-index  : 99.03142;
  }

  2% {
    transform: matrix3d(0.58298, 0, 0, 0, 0, 0.58298, 0, 0, 0, 0, 1, 0, -130.4234, -62.342, 0, 1);
    z-index  : 99.04894;
  }

  3% {
    transform: matrix3d(0.59007, 0, 0, 0, 0, 0.59007, 0, 0, 0, 0, 1, 0, -125.4342, -68.3422, 0, 1);
    z-index  : 99.07022;
  }

  4% {
    transform: matrix3d(0.59839, 0, 0, 0, 0, 0.59839, 0, 0, 0, 0, 1, 0, -120.2343, -74.2342, 0, 1);
    z-index  : 99.09517;
  }

  5% {
    transform: matrix3d(0.6079, 0, 0, 0, 0, 0.6079, 0, 0, 0, 0, 1, 0, -113.3244, -80.63055, 0, 1);
    z-index  : 99.12369;
  }

  6% {
    transform: matrix3d(0.61856, 0, 0, 0, 0, 0.61856, 0, 0, 0, 0, 1, 0, -105.3432, -86.43264, 0, 1);
    z-index  : 99.15567;
  }

  7% {
    transform: matrix3d(0.63033, 0, 0, 0, 0, 0.63033, 0, 0, 0, 0, 1, 0, -96.2342, -90.9015, 0, 1);
    z-index  : 99.19099;
  }

  8% {
    transform: matrix3d(0.64316, 0, 0, 0, 0, 0.64316, 0, 0, 0, 0, 1, 0, -87.3242, -96.05106, 0, 1);
    z-index  : 99.22949;
  }

  9% {
    transform: matrix3d(0.65701, 0, 0, 0, 0, 0.65701, 0, 0, 0, 0, 1, 0, -77.3454, -99.89652, 0, 1);
    z-index  : 99.27103;
  }

  10% {
    transform: matrix3d(0.67182, 0, 0, 0, 0, 0.67182, 0, 0, 0, 0, 1, 0,-65.2342, -95.45427, 0, 1);
    z-index  : 99.31546;
  }

  11% {
    transform: matrix3d(0.68753, 0, 0, 0, 0, 0.68753, 0, 0, 0, 0, 1, 0, -53.3234, -90.74182, 0, 1);
    z-index  : 99.36258;
  }

  12% {
    transform: matrix3d(0.70407, 0, 0, 0, 0, 0.70407, 0, 0, 0, 0, 1, 0, -41.2342, -84.77778, 0, 1);
    z-index  : 99.41222;
  }

  13% {
    transform: matrix3d(0.72139, 0, 0, 0, 0, 0.72139, 0, 0, 0, 0, 1, 0, -28.2344, -78.58172, 0, 1);
    z-index  : 99.46418;
  }

  14% {
    transform: matrix3d(0.73942, 0, 0, 0, 0, 0.73942, 0, 0, 0, 0, 1, 0, -14.3433, -72.17414, 0, 1);
    z-index  : 99.51826;
  }

  15% {
    transform: matrix3d(0.75808, 0, 0, 0, 0, 0.75808, 0, 0, 0, 0, 1, 0, -0, -68.57636, 0, 1);
    z-index  : 99.57424;
  }

  16% {
    transform: matrix3d(0.7773, 0, 0, 0, 0, 0.7773, 0, 0, 0, 0, 1, 0, 16.3423, -64.81045, 0, 1);
    z-index  : 99.6319;
  }

  17% {
    transform: matrix3d(0.797, 0, 0, 0, 0, 0.797, 0, 0, 0, 0, 1, 0, 32.2423, -60.89914, 0, 1);
    z-index  : 99.69101;
  }

  18% {
    transform: matrix3d(0.81711, 0, 0, 0, 0, 0.81711, 0, 0, 0, 0, 1, 0, 44.3543, -58.86574, 0, 1);
    z-index  : 99.75134;
  }

  19% {
    transform: matrix3d(0.83755, 0, 0, 0, 0, 0.83755, 0, 0, 0, 0, 1, 0, 60.2342, -56.73401, 0, 1);
    z-index  : 99.81266;
  }

  20% {
    transform: matrix3d(0.85824, 0, 0, 0, 0, 0.85824, 0, 0, 0, 0, 1, 0, 76.5345, -54.52811, 0, 1);
    z-index  : 99.87472;
  }

  21% {
    transform: matrix3d(0.87909, 0, 0, 0, 0, 0.87909, 0, 0, 0, 0, 1, 0, 92.2343, -53.27248, 0, 1);
    z-index  : 99.93728;
  }

  22% {
    transform: matrix3d(0.90003, 0, 0, 0, 0, 0.90003, 0, 0, 0, 0, 1, 0, 108.4324, -52.8834, 0, 1);
    z-index  : 100.00008;
  }

  23% {
    transform: matrix3d(0.9, 0, 0, 0, 0, 0.9, 0, 0, 0, 0, 1, 0, 124.23423, -51.45435,0, 1);
    z-index  : 100;
  }

  24% {
    transform: matrix3d(0.92093, 0, 0, 0, 0, 0.92093, 0, 0, 0, 0, 1, 0,134.3433, -50, 0, 1);
    z-index  : 100.06279;
  }

  25% {
    transform: matrix3d(0.94178, 0, 0, 0, 0, 0.94178, 0, 0, 0, 0, 1, 0, 149.3432, -48.3243, 0, 1);
    z-index  : 100.12533;
  }

  26% {
    transform: matrix3d(0.96246, 0, 0, 0, 0, 0.96246, 0, 0, 0, 0, 1, 0,165.3423, -46.73813, 0, 1);
    z-index  : 100.18738;
  }

  27% {
    transform: matrix3d(0.9829, 0, 0, 0, 0, 0.9829, 0, 0, 0, 0, 1, 0, 181.3423, -43.86899, 0, 1);
    z-index  : 100.24869;
  }

  28% {
    transform: matrix3d(1.00301, 0, 0, 0, 0, 1.00301, 0, 0, 0, 0, 1, 0, 197.3243, -40.9017, 0, 1);
    z-index  : 100.30902;
  }

  29% {
    transform: matrix3d(1.02271, 0, 0, 0, 0, 1.02271, 0, 0, 0, 0, 1, 0, 213.2342, -36.81246, 0, 1);
    z-index  : 100.36812;
  }

  30% {
    transform: matrix3d(1.04193, 0, 0, 0, 0, 1.04193, 0, 0, 0, 0, 1, 0, 229.32432, -32.57793, 0, 1);
    z-index  : 100.42578;
  }

  31% {
    transform: matrix3d(1.06058, 0, 0, 0, 0, 1.06058, 0, 0, 0, 0, 1, 0, 245.3432, -28.17537, 0, 1);
    z-index  : 100.48175;
  }

  32% {
    transform: matrix3d(1.07861, 0, 0, 0, 0, 1.07861, 0, 0, 0, 0, 1, 0, 261.3242, -24.58268, 0, 1);
    z-index  : 100.53583;
  }

  33% {
    transform: matrix3d(1.09593, 0, 0, 0, 0, 1.09593, 0, 0, 0, 0, 1, 0, 269.2342, -20.77853, 0, 1);
    z-index  : 100.58779;
  }

  34% {
    transform: matrix3d(1.11247, 0, 0, 0, 0, 1.11247, 0, 0, 0, 0, 1, 0, 255.3434, -14.7424, 0, 1);
    z-index  : 100.63742;
  }

  35% {
    transform: matrix3d(1.12818, 0, 0, 0, 0, 1.12818, 0, 0, 0, 0, 1, 0, 243.42343, -8.45471, 0, 1);
    z-index  : 100.68455;
  }

  36% {
    transform: matrix3d(1.14299, 0, 0, 0, 0, 1.14299, 0, 0, 0, 0, 1, 0, 231.3423, -2.89686, 0, 1);
    z-index  : 100.72897;
  }

  37% {
    transform: matrix3d(1.15684, 0, 0, 0, 0, 1.15684, 0, 0, 0, 0, 1, 0, 217.3432, 4.05132, 0, 1);
    z-index  : 100.77051;
  }

  38% {
    transform: matrix3d(1.16967, 0, 0, 0, 0, 1.16967, 0, 0, 0, 0, 1, 0, 207.3242, 10.9017, 0, 1);
    z-index  : 100.80902;
  }

  39% {
    transform: matrix3d(1.18144, 0, 0, 0, 0, 1.18144, 0, 0, 0, 0, 1, 0,195.3423, 16.43279, 0, 1);
    z-index  : 100.84433;
  }

  40% {
    transform: matrix3d(1.1921, 0, 0, 0, 0, 1.1921, 0, 0, 0, 0, 1, 0, 183.2343, 22.63067, 0, 1);
    z-index  : 100.87631;
  }

  41% {
    transform: matrix3d(1.20161, 0, 0, 0, 0, 1.20161, 0, 0, 0, 0, 1, 0, 172.23432, 28.48271, 0, 1);
    z-index  : 100.90483;
  }

  42% {
    transform: matrix3d(1.20993, 0, 0, 0, 0, 1.20993, 0, 0, 0, 0, 1, 0, 166.32432, 34.97765, 0, 1);
    z-index  : 100.92978;
  }

  43% {
    transform: matrix3d(1.21702, 0, 0, 0, 0, 1.21702, 0, 0, 0, 0, 1, 0, 158.3242, 36.10565, 0, 1);
    z-index  : 100.95106;
  }

  44% {
    transform: matrix3d(1.22286, 0, 0, 0, 0, 1.22286, 0, 0, 0, 0, 1, 0, 151.2342, 38.85832, 0, 1);
    z-index  : 100.96858;
  }

  45% {
    transform: matrix3d(1.22743, 0, 0, 0, 0, 1.22743, 0, 0, 0, 0, 1, 0, 145.3422, 40.22873, 0, 1);
    z-index  : 100.98229;
  }

  46% {
    transform: matrix3d(1.22743, 0, 0, 0, 0, 1.22743, 0, 0, 0, 0, 1, 0, 140.3232, 42.21147, 0, 1);
    z-index  : 100.99211;
  }

  47% {
    transform: matrix3d(1.22743, 0, 0, 0, 0, 1.22743, 0, 0, 0, 0, 1, 0, 138.3222, 45.80267, 0, 1);
    z-index  : 100.99803;
  }

  48% {
    transform: matrix3d(1.22743, 0, 0, 0, 0, 1.22743, 0, 0, 0, 0, 1, 0,136.2342, 47.242, 0, 1);
    z-index  : 101;
  }
  49% {
    transform: matrix3d(1.22743, 0, 0, 0, 0, 1.22743, 0, 0, 0, 0, 1, 0,135 , 49.9453, 0, 1);
    z-index  : 100.99803;
  }

  50% {
    transform: matrix3d(1.22743, 0, 0, 0, 0, 1.22743, 0, 0, 0, 0, 1, 0, 134.2334, 55.21147, 0, 1);
    z-index  : 100.99211;
  }

  51% {
    transform: matrix3d(1.22743, 0, 0, 0, 0, 1.22743, 0, 0, 0, 0, 1, 0, 132.2342, 61.22873, 0, 1);
    z-index  : 100.98229;
  }

  52% {
    transform: matrix3d(1.22286, 0, 0, 0, 0, 1.22286, 0, 0, 0, 0, 1, 0, 129.4324, 66.85832, 0, 1);
    z-index  : 100.96858;
  }

  53% {
    transform: matrix3d(1.21702, 0, 0, 0, 0, 1.21702, 0, 0, 0, 0, 1, 0,125.3454, 72.10565, 0, 1);
    z-index  : 100.95106;
  }

  54% {
    transform: matrix3d(1.20993, 0, 0, 0, 0, 1.20993, 0, 0, 0, 0, 1, 0, 120.2342, 78.97765, 0, 1);
    z-index  : 100.92978;
  }

  55% {
    transform: matrix3d(1.20161, 0, 0, 0, 0, 1.20161, 0, 0, 0, 0, 1, 0, 115.5344, 84.48271, 0, 1);
    z-index  : 100.90483;
  }

  56% {
    transform: matrix3d(1.1921, 0, 0, 0, 0, 1.1921, 0, 0, 0, 0, 1, 0, 109.2423, 90.63067, 0, 1);
    z-index  : 100.87631;
  }

  57% {
    transform: matrix3d(1.18144, 0, 0, 0, 0, 1.18144, 0, 0, 0, 0, 1, 0, 101.2343, 94.43279, 0, 1);
    z-index  : 100.84433;
  }

  58% {
    transform: matrix3d(1.16967, 0, 0, 0, 0, 1.16967, 0, 0, 0, 0, 1, 0, 92.2423, 99.9017, 0, 1);
    z-index  : 100.80902;
  }

  59% {
    transform: matrix3d(1.15684, 0, 0, 0, 0, 1.15684, 0, 0, 0, 0, 1, 0, 83.3242, 93.05132, 0, 1);
    z-index  : 100.77051;
  }

  60% {
    transform: matrix3d(1.14299, 0, 0, 0, 0, 1.14299, 0, 0, 0, 0, 1, 0, 73.2423, 87.89686, 0, 1);
    z-index  : 100.72897;
  }

  61% {
    transform: matrix3d(1.12818, 0, 0, 0, 0, 1.12818, 0, 0, 0, 0, 1, 0, 61.2324, 81.45471, 0, 1);
    z-index  : 100.68455;
  }

  62% {
    transform: matrix3d(1.11247, 0, 0, 0, 0, 1.11247, 0, 0, 0, 0, 1, 0, 49.3242, 76.7424, 0, 1);
    z-index  : 100.63742;
  }

  63% {
    transform: matrix3d(1.09593, 0, 0, 0, 0, 1.09593, 0, 0, 0, 0, 1, 0, 35.2342, 71.77853, 0, 1);
    z-index  : 100.58779;
  }

  64% {
    transform: matrix3d(1.07861, 0, 0, 0, 0, 1.07861, 0, 0, 0, 0, 1, 0, 21.2343, 68.58268, 0, 1);
    z-index  : 100.53583;
  }

  65% {
    transform: matrix3d(1.06058, 0, 0, 0, 0, 1.06058, 0, 0, 0, 0, 1, 0, 7.3442, 66.17537, 0, 1);
    z-index  : 100.48175;
  }

  66% {
    transform: matrix3d(1.04193, 0, 0, 0, 0, 1.04193, 0, 0, 0, 0, 1, 0, -7.2342, 64.57793, 0, 1);
    z-index  : 100.42578;
  }

  67% {
    transform: matrix3d(1.02271, 0, 0, 0, 0, 1.02271, 0, 0, 0, 0, 1, 0, -23.3242, 62.81246, 0, 1);
    z-index  : 100.36812;
  }

  68% {
    transform: matrix3d(1.00301, 0, 0, 0, 0, 1.00301, 0, 0, 0, 0, 1, 0, -38.4243, 60.9017, 0, 1);
    z-index  : 100.30902;
  }

  69% {
    transform: matrix3d(0.9829, 0, 0, 0, 0, 0.9829, 0, 0, 0, 0, 1, 0, -52.4223, 58.86899, 0, 1);
    z-index  : 100.24869;
  }

  70% {
    transform: matrix3d(0.96246, 0, 0, 0, 0, 0.96246, 0, 0, 0, 0, 1, 0, -69.3242, 56.73813, 0, 1);
    z-index  : 100.18738;
  }

  71% {
    transform: matrix3d(0.94178, 0, 0, 0, 0, 0.94178, 0, 0, 0, 0, 1, 0,-86.2342, 54.53332, 0, 1);
    z-index  : 100.12533;
  }

  72% {
    transform: matrix3d(0.92093, 0, 0, 0, 0, 0.92093, 0, 0, 0, 0, 1, 0, -103.43243, 52.27905, 0, 1);
    z-index  : 100.06279;
  }

  73% {
    transform: matrix3d(0.9, 0, 0, 0, 0, 0.9, 0, 0, 0, 0, 1, 0, -120.43232, 51.4354, 0, 1);
    z-index  : 100;
  }

  74% {
    transform: matrix3d(0.87907, 0, 0, 0, 0, 0.87907, 0, 0, 0, 0, 1, 0, -135, 50, 0, 1);
    z-index  : 99.93721;
  }
  75% {
    transform: matrix3d(0.85822, 0, 0, 0, 0, 0.85822, 0, 0, 0, 0, 1, 0, -151.332,0, 49.3244, 1);
    z-index  : 99.87467;
  }

  76% {
    transform: matrix3d(0.83754, 0, 0, 0, 0, 0.83754, 0, 0, 0, 0, 1, 0, -167.3242, 44.3532, 0, 1);
    z-index  : 99.81262;
  }

  77% {
    transform: matrix3d(0.8171, 0, 0, 0, 0, 0.8171, 0, 0, 0, 0, 1, 0, -184.2343, 39.86899, 0, 1);
    z-index  : 99.75131;
  }

  78% {
    transform: matrix3d(0.79699, 0, 0, 0, 0, 0.79699, 0, 0, 0, 0, 1, 0, -201.2311, 33.9017, 0, 1);
    z-index  : 99.69098;
  }

  79% {
    transform: matrix3d(0.77729, 0, 0, 0, 0, 0.77729, 0, 0, 0, 0, 1, 0, -217.3432, 27.81246, 0, 1);
    z-index  : 99.63188;
  }

  80% {
    transform: matrix3d(0.75807, 0, 0, 0, 0, 0.75807, 0, 0, 0, 0, 1, 0, -233.1321, 21.57793, 0, 1);
    z-index  : 99.57422;
  }

  81% {
    transform: matrix3d(0.73942, 0, 0, 0, 0, 0.73942, 0, 0, 0, 0, 1, 0, -248.4234, 15.17537, 0, 1);
    z-index  : 99.51825;
  }

  82% {
    transform: matrix3d(0.72139, 0, 0, 0, 0, 0.72139, 0, 0, 0, 0, 1, 0, -264.4324, 9.58268, 0, 1);
    z-index  : 99.46417;
  }

  83% {
    transform: matrix3d(0.70407, 0, 0, 0, 0, 0.70407, 0, 0, 0, 0, 1, 0, -262.3242, 3.77853, 0, 1);
    z-index  : 99.41221;
  }

  84% {
    transform: matrix3d(0.68753, 0, 0, 0, 0, 0.68753, 0, 0, 0, 0, 1, 0, -248.3243, -3.7424, 0, 1);
    z-index  : 99.36258;
  }

  85% {
    transform: matrix3d(0.67182, 0, 0, 0, 0, 0.67182, 0, 0, 0, 0, 1, 0, -234.424, -9.45471, 0, 1);
    z-index  : 99.31545;
  }

  86% {
    transform: matrix3d(0.65701, 0, 0, 0, 0, 0.65701, 0, 0, 0, 0, 1, 0, -222.4324, -15.89686, 0, 1);
    z-index  : 99.27103;
  }

  87% {
    transform: matrix3d(0.64316, 0, 0, 0, 0, 0.64316, 0, 0, 0, 0, 1, 0, -210.2343, -21.05132, 0, 1);
    z-index  : 99.22949;
  }

  88% {
    transform: matrix3d(0.63033, 0, 0, 0, 0, 0.63033, 0, 0, 0, 0, 1, 0, -198.2432, -26.9017, 0, 1);
    z-index  : 99.19098;
  }

  89% {
    transform: matrix3d(0.61856, 0, 0, 0, 0, 0.61856, 0, 0, 0, 0, 1, 0, -188.2342, -30.43279, 0, 1);
    z-index  : 99.15567;
  }

  90% {
    transform: matrix3d(0.6079, 0, 0, 0, 0, 0.6079, 0, 0, 0, 0, 1, 0, -179.4322, -34.63067, 0, 1);
    z-index  : 99.12369;
  }

  91% {
    transform: matrix3d(0.59839, 0, 0, 0, 0, 0.59839, 0, 0, 0, 0, 1, 0, -170.3242, -38.4827, 0, 1);
    z-index  : 99.09517;
  }

  92% {
    transform: matrix3d(0.59007, 0, 0, 0, 0, 0.59007, 0, 0, 0, 0, 1, 0, -162.2422, -40.97765, 0, 1);
    z-index  : 99.07022;
  }

  93% {
    transform: matrix3d(0.58298, 0, 0, 0, 0, 0.58298, 0, 0, 0, 0, 1, 0, -155.4322, -41.10565, 0, 1);
    z-index  : 99.04894;
  }

  94% {
    transform: matrix3d(0.57714, 0, 0, 0, 0, 0.57714, 0, 0, 0, 0, 1, 0, -149.2342, -43.85831, 0, 1);
    z-index  : 99.03142;
  }

  95% {
    transform: matrix3d(0.57257, 0, 0, 0, 0, 0.57257, 0, 0, 0, 0, 1, 0, -144.2422, -46.22872, 0, 1);
    z-index  : 99.01771;
  }

  96% {
    transform: matrix3d(0.5693, 0, 0, 0, 0, 0.5693, 0, 0, 0, 0, 1, 0, -142.4234, -48.21146, 0, 1);
    z-index  : 99.00789;
  }

  97% {
    transform: matrix3d(0.56732, 0, 0, 0, 0, 0.56732, 0, 0, 0, 0, 1, 0, -140.42342, -49.80266, 0, 1);
    z-index  : 99.00197;
  }

  98% {
    transform: matrix3d(0.56667, 0, 0, 0, 0, 0.56667, 0, 0, 0, 0, 1, 0, -138.34242, -49.99999, 0, 1);
    z-index  : 99;
  }

  99% {
    transform: matrix3d(0.56732, 0, 0, 0, 0, 0.56732, 0, 0, 0, 0, 1, 0, -136.234, -49.80266, 0, 1);
    z-index  : 99.00197;
  }

  100% {
    transform: matrix3d(0.5693, 0, 0, 0, 0, 0.5693, 0, 0, 0, 0, 1, 0, -135.2432, -49.21145, 0, 1);
    z-index  : 99.00789;
  }
}
/* 你的样式代码 */
</style>
