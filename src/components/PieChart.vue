<script>
import { Doughnut } from "vue-chartjs";

export default {
  name: "chart",
  extends: Doughnut,
  props: ["data", "options"],
  mounted() {
    let gradient = this.$refs.canvas
      .getContext("2d")
      .createLinearGradient(0, 0, 0, 450);
    gradient.addColorStop(0, "#d25337");
    gradient.addColorStop(0.3, "#744174");
    gradient.addColorStop(1, "#543a8a");

    this.data.datasets[0].backgroundColor = [gradient, "#f1e7db"];
    this.renderChart(this.data, this.options);
  }
};
</script>

<style>
</style>
