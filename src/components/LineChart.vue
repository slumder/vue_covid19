<script>
import {Line} from "vue-chartjs";

export default {
  extends: Line,

  // 接收 父參數
  props: {
    label: {
      type: String,
    },
    chartData: {
      type: Array,
    },
    options: {
      type: Object,
    },
    chartColorOptions: {
      type: Object,
    },
  },
  mounted() {
    // const dates = [
    //   "2021/01/01",
    //   "2021/01/02",
    //   "2021/01/03",
    //   "2021/01/04",
    //   "2021/01/05",
    //   "2021/01/06",
    // ];
    // const totals = [50, 40, 71, 51, 25, 49];
    const dates = this.chartData.map((d) => d.date).reverse();
    const totals = this.chartData.map((d) => d.total).reverse();

    this.renderChart(
      {
        labels: dates,
        datasets: [
          {
            label: this.label,
            data: totals,
            ...this.chartColorOptions,
          },
        ],
      },
      // {
      //   responsive: true,
      //   maintainAspectRatio: false,
      // }
      this.options
    );
  },
};
</script>