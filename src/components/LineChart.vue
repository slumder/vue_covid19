<script>
import { Line } from "vue-chartjs";

export default {
  extends: Line,
  mounted() {
    const dates = [
      "2021/01/01",
      "2021/01/02",
      "2021/01/03",
      "2021/01/04",
      "2021/01/05",
      "2021/01/06",
    ];
    const totals = [50, 40, 71, 51, 25, 49];

    this.renderChart(
      {
        labels: dates,
        datasets: [
          {
            label: "demo",
            data: totals,
          },
        ],
      },
      {
        responsive: true,
        maintainAspectRatio: false,
      }
    );
  },
};
</script>