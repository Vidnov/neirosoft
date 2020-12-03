
<script>
import VueChartJs from "vue-chartjs";
export default {
  name: "Diagramm",
  extends: VueChartJs.Doughnut,
  components: {},
  data() {
    return {
      options: {
        responsive: true,
        maintainAspectRatio: false,
        layout: {
          padding: {
            left: -430,
            right: 0,
            top: 0,
            bottom: 0,
          },
        },
        elements: {
          point: {
            radius: 3,
            pointStyle: "circle",
          },
        },
        title: {},
        legend: {
          align: "center",
          position: "right",
          fullWidth: true,
          labels: {
            usePointStyle: true,
            boxWidth: 35,
            fontSize: 22,
            padding: 30,
          },
        },
      },
    };
  },

  props: ["departments", "employees", "color"],

  mounted() {
    this.renderChart(
      {
        labels: this._props.departments,
        datasets: [
          {
            label: this._props.departments,
            backgroundColor: this._props.color,
            data: this._props.employees,
          },
        ],
        options: {
          legend: {
            position: "right",
          },
        },
      },
      this.options
    );
  },
};
</script>

<style lang="scss" >
.chartjs-size-monitor-shrink {
  background-color: black;
}
</style>
